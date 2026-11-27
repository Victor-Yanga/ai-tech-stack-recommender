Project 3: AI Recommendation Logic (Tech Stack Recommender)

DecodeLabs AI Internship, Batch 2026. Author: Victor Usoh.

A content-based recommendation engine that matches a user's skills to job roles and suggests the tools to learn next.

How it works

1. Ingestion: the user enters at least three skills (unknown skills are reported and ignored).
2. Scoring: skills and job roles are turned into TF-IDF vectors in a shared vocabulary, then compared with cosine similarity.
3. Sorting: roles are ranked from best to worst match.
4. Filtering: only the Top 3 roles with a score above zero are shown, with a match percentage and tools to learn.

If nothing matches, a cold-start fallback suggests popular starter roles.

Files

• tech_stack_recommender.py: the program
• raw_skills.csv: 12 job roles with their core skills and tools

Run it

pip install scikit-learn pandas
python tech_stack_recommender.py

Or pass skills directly: python tech_stack_recommender.py "Python, Cloud, Automation"

Example

Input: Python, Cloud, Automation

1. Data Engineer (51% match)
2. Cloud Engineer (45% match)
3. DevOps Engineer (39% match)

Limitations and next steps

• The dataset is small and written by hand, so recommendations reflect only these 12 roles.
• Next: use a larger dataset, add skill weighting, and try Jaccard similarity for comparison.
