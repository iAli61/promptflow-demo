step 1) Run Chat with pdf flow
```
pf flow test --flow . --inputs question="What is the name of the new language representation model introduced in the document?" pdf_url="https://arxiv.org/pdf/1810.04805.pdf"
```
step 2) evaluate the run with Q&A RAG evaluation flow
```
pf run create --flow . --data ./data.jsonl --column-mapping question='${data.question}' answer='${data.answer}' documents='${data.documents}' metrics='gpt_groundedness' --stream
```