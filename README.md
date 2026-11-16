    '<sub>Each repository documents its architecture, implementation choices, and known limitations.</sub>\n\n'
    '## 🧰 Engineering toolkit\n\nI use'
)
for label in [
    '01 / Languages and application frameworks',
    '02 / Distributed workflows and data',
    '03 / AI systems and evaluation',
    '04 / Interfaces, testing, and delivery'
]:
    replace_once(f'{label}\n<p>', f'### {label}\n\n<p>')
for prev, next_header in [
    ('usable products.', '02'),
    ('vector-backed retrieval.', '03'),
    ('independent AI applications.', '04')
]:
    replace_once(f'{prev}\n### {next_header}', f'{prev}\n\n### {next_header}')

replace_once(
    '<sub>Also hands-on with: LangGraph state and memory, SQLAlchemy/SQLModel, Alembic, REST APIs, cross-encoder reranking, GitHub release workflows, and agent-assisted testing.</sub>\n'
    '✍️ Writing about AI, from first principles\n'
    "I publish Generative AI from First Principles on Medium. It's a series that builds intuition before introducing the abstractions, from how neural networks learn to why attention changed sequence modeling.\n"
    '- Transformers explained simply: why attention replaced RNNs, LSTMs, and GRUs\n'
    '  Attention, Q/K/V, positional information, multi-head attention, and the architectural shift from recurrence.\n'
    '- How models learn: forward pass, loss, gradient descent, and backpropagation\n'
    '  A simple, step-by-step explanation of the core training loop.\n'
    '- Long short-term memory: understanding LSTM networks\n'
    '  Hidden states, cell states, gates, and how sequence models preserve context.\n'
    '<p align="center">\n'
    '  <a href="https://medium.com/@bhavikapawani4444"><img src="https://img.shields.io/badge/Read%20more%20on%20Medium-111827?style=for-the-badge&logo=medium&logoColor=white" alt="Read more on Medium" /></a>\n'
    '</p>',
    '<sub>Also hands-on with: LangGraph state and memory, SQLAlchemy/SQLModel, Alembic, REST APIs, cross-encoder reranking, GitHub release workflows, and agent-assisted testing.</sub>\n\n'
    '## ✍️ Writing and perspectives\n\n'
    'I share my perspectives on software engineering, applied AI, and building reliable AI systems on [X / Twitter](https://x.com/stacktraceee). On [Medium](https://medium.com/@bhavikapawani4444), I publish deeper explanations in my *Generative AI from First Principles* series, building intuition before introducing abstractions.\n\n'
    "Topics I've written about include:\n\n"
    '- Transformers and why attention changed sequence modeling — Q/K/V, positional information, and multi-head attention.\n'
    '- How models learn — forward passes, loss, gradient descent, and backpropagation.\n'
    '- LSTM networks — hidden states, cell states, and gates for sequence memory.\n\n'
    '<p align="center">\n'
    '  <a href="https://x.com/stacktraceee"><img src="https://img.shields.io/badge/Thoughts%20on%20X-0F172A?style=for-the-badge&logo=x&logoColor=white" alt="Perspectives on X" /></a>\n'
    '  <a href="https://medium.com/@bhavikapawani4444"><img src="https://img.shields.io/badge/Articles%20on%20Medium-111827?style=for-the-badge&logo=medium&logoColor=white" alt="Articles on Medium" /></a>\n'
    '</p>'
)
while '\n\n\n' in text:
    text = text.replace('\n\n\n', '\n\n')

checks = {
    'BuyRightAgents project': '01 · BuyRightAgents' in text,
    'X links': text.count('href="https://x.com/stacktraceee"') == 2,
    'Medium links': text.count('href="https://medium.com/@bhavikapawani4444"') == 2,
    'All five projects': all(s in text for s in ['02 · VibeCodeFolks', '03 · GenAI Knowledge Platform', '04 · AI Research Browser', '05 · Grounded AI Assistant']),
    'Section headings': all(s in text for s in ['## 🏗️', '## 🚀', '## 🧰', '## ✍️']),
    'Existing screenshots': text.count('raw.githubusercontent.com/BHAVIKA44') == 4,
}
if not all(checks.values()):
    raise RuntimeError(f'Validation failed: {checks}')
path.write_text(text, encoding='utf-8')
print('Updated README.md successfully. Review with: git diff -- README.md')
