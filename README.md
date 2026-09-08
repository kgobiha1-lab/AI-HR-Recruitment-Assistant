The AI HR Recruitment Assistant is an autonomous agent that automates the first stage of the hiring process — resume screening. Given a set of resumes and a knowledge base of job descriptions, the agent retrieves the most relevant job for each candidate using Retrieval-Augmented Generation (RAG), scores the candidate against that job's required and preferred skills using a dedicated scoring tool, and generates interview questions tailored to the candidate's specific skill matches and gaps.
The system is built around three core components:
RAG (Retrieval) — A knowledge base of job descriptions is indexed, and for every incoming resume, the agent retrieves the single best-matching job description using keyword-relevance retrieval.
Tools — Three purpose-built tools support the agent:
parse_resume — extracts candidate name, contact details, skills, and years of experience from raw resume text
calculate_match_score — computes a weighted 0–100 match score based on required skills (60%), preferred skills (15%), and experience (25%)
generate_interview_questions — produces technical, gap-probing, and behavioral interview questions specific to each candidate
Memory — Every screening result is stored persistently, enabling the agent to generate a ranked shortlist of top candidates for any job role on demand.
The complete pipeline — parse → retrieve → score → generate questions → store — runs automatically for a batch of resumes and produces a full screening report along with a ranked shortlist per job title.
Tech Stack
Python 3.8+ (standard library only, no external dependencies)
Sample Results
3 sample resumes were screened against 5 sample job descriptions, achieving accurate role matching and clear, explainable scoring (e.g., a candidate with matching Python/SQL/Git skills scored 100/100 for a Backend Python Developer role, while a mismatched candidate scored 0/100).
