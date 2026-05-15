mkdir BHAVIKA44 && cd BHAVIKA44
git init
cat > README.md << 'EOF'
# Hi, I’m Bhavika Pawani

Software engineer focused on building reliable, scalable systems across scientific and fintech domains.  
Recently, I’ve been deeply exploring GenAI systems engineering, especially agentic workflows, LLM runtime reliability, and observability.

## What I Work On

- Workflow-driven platforms for complex operations
- Backend and full-stack product engineering
- Data-heavy systems with strong traceability and reliability
- GenAI applications with multi-agent orchestration and grounded outputs

## Recent Focus: GenAI Engineering

- Lightweight multi-agent orchestration with LangGraph
- Provider-aware LLM gateway design (routing, retries, fallbacks)
- Citation-grounded research workflows
- LangSmith + app-level observability patterns
- Reliability-first API and platform design

## Selected Experience Highlights

- Engineered workflows spanning sequencing, expression, purification, and related scientific operations for large-scale biopharma R&D teams across multiple sites.
- Built configuration-driven services to reduce developer effort and speed up onboarding of new workflow variants.
- Developed client-facing tools and internal automation to improve delivery velocity and operational efficiency.

## Writing

I share practical learnings on engineering and GenAI here:  
- [Medium](https://medium.com/@bhavikapawani4444)

## Connect

- [LinkedIn](#)  
- [Medium](https://medium.com/@bhavikapawani4444)
EOF
git add README.md
git commit -m "Add profile README"
git branch -M main
git remote add origin https://github.com/BHAVIKA44/BHAVIKA44.git
git push -u origin main
