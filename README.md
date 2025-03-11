# Generative Information Extraction from scientific literature

This notebook reads .pdf (pyPDFloader), selects texts based on inclusion and exclusion criteria (with GPT-4o)and finally returns structured output based on a schema (with GPT-o3-mini). API Key required.
It is based on this [Langchain tutorial](https://python.langchain.com/docs/tutorials/extraction/).

## Notes on LLM choice
When selecting an LLM, consider the following trade-off:
Reasoning models like o3 tend to be more accurate in information extraction. However, their outputs are less consistent and reproducible. Meaning: Running the same script twice may yield different results. The overall semantics of the output remain largely identical but depending on the usecase this might not be satisfactory. Measures to move towards reproducability are 
- the structured output / **JsonOutputParser** minimizes generative freedom
- **None** as default in prompt and pydantic schema
- **temperature=0** --> But currently o3 does not accept this parameter



