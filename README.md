# Generative AI in Healthcare: Tutorial with Synthetic Data

This repository contains a Jupyter Notebook (`LLM_Tutorial.ipynb`) demonstrating the application of generative AI, specifically OpenAI's GPT-4o model, to healthcare tasks using synthetic patient data. The tutorial explores various prompt engineering techniques to address healthcare challenges, such as medical history summarization, tabular data conversion, disease prediction, medical note simplification, and medical question answering.

## Project Overview

**Objective**: Leverage Large Language Models (LLMs) to enhance healthcare processes using synthetic data from the Synthea dataset. The notebook showcases:
- Summarizing medical information with evaluation (ROUGE scores)
- Converting tabular data to narratives using in-context learning, few-shot learning, chain-of-thought, and tree-of-thought reasoning
- Predicting potential diseases based on patient characteristics
- Simplifying medical notes for a 10-year-old audience
- Answering patient questions with reasoned responses
- Advanced applications like diagnostic reasoning, treatment plans, and care planning

**Healthcare Issue**: Improving accessibility, efficiency, and patient understanding in healthcare through AI-driven solutions.

**Assignment Context**: This project fulfills the requirements of a course assignment to apply generative AI to healthcare, using safe, synthetic data to comply with privacy regulations.

## Dataset

- **Source**: [Synthea Synthetic Patient Data](https://synthea.mitre.org/downloads)
- **Details**:
  - Size: 7 MB, 100 synthetic patients
  - Files: `patients.csv`, `conditions.csv`, `encounters.csv`
  - De-identified, suitable for use with OpenAI API
- **Preprocessing**:
  - Merged patient, condition, and encounter data
  - Calculated patient ages
  - Sampled 50 records for efficient processing

## Requirements

To run the notebook, install the following Python packages:
```bash
pip install pandas nltk rouge-score openai
```

Additional setup:
- **OpenAI API Key**: Set as an environment variable (`OPENAI_API_KEY`). Replace `"PUT YOUR OWN KEY"` in the notebook with your key.
- **NLTK Data**: The notebook downloads the `punkt` package automatically.
- **Synthea Data**: Download from [Synthea](https://synthea.mitre.org/downloads) and update the `data_path` in the notebook to point to your local directory.

## Running the Notebook

1. Clone this repository:
   ```bash
   git clone https://github.com/hbk008/LLM-Tutorial.git
   ```
2. Install dependencies (see above).
3. Download Synthea data and update the file path in the notebook (`data_path` variable in Step 1).
4. Set your OpenAI API key as an environment variable or directly in the notebook.
5. Open and run `LLM_Tutorial.ipynb` using Jupyter Notebook or JupyterLab:
   ```bash
   jupyter notebook LLM_Tutorial.ipynb
   ```

## Notebook Structure

- **Step 0**: Setup (install packages, configure OpenAI client)
- **Step 1**: Load and preprocess Synthea data
- **Step 2**: Summarize medical histories (in-context and few-shot learning)
- **Step 3**: Convert tabular data to narratives (chain-of-thought, tree-of-thought)
- **Step 4**: Predict diseases (few-shot learning)
- **Step 5**: Simplify medical notes for children (in-context learning)
- **Step 6**: Evaluate outputs (ROUGE scores, token counts, readability)
- **Step 7**: Medical question answering with reasoning
- **Step 8**: Advanced applications (diagnostic reasoning, treatment plans, care plans)
- **Conclusion**: Summary and future extensions

## Prompt Engineering Techniques

- **In-Context Learning**: Single examples for summarization and simplification
- **Few-Shot Learning**: Multiple examples for summarization and prediction
- **Chain-of-Thought (CoT)**: Step-by-step reasoning for narrative conversion
- **Tree-of-Thought (ToT)**: Multiple narrative styles (clinical, patient-friendly)

## Evaluation

- **Summarization**: ROUGE-1 and ROUGE-L scores (few-shot outperformed in-context)
  - In-context: ROUGE-1: 0.1364, ROUGE-L: 0.1364
  - Few-shot: ROUGE-1: 0.2143, ROUGE-L: 0.2143
- **Narratives**: Qualitative assessment of clarity and completeness
- **Disease Prediction**: Noted need for clinical validation
- **Simplification**: Readability metrics (e.g., avg. word length: 4.32 chars, 25 words)
- **Token Counts**: Measured output verbosity across tasks

## Future Improvements

- Scale to larger datasets
- Compare different LLMs (e.g., GPT-4o vs. PMC-LLaMA)
- Use advanced evaluation metrics (BLEU, BERTScore)
- Fine-tune models for healthcare tasks
- Add safety guardrails for medical content
- Explore multimodal applications (e.g., medical imaging)

## References

- [Synthea Dataset](https://synthea.mitre.org/downloads)
- [OpenAI API Documentation](https://platform.openai.com/docs/)
- [In-Context Learning](https://aclanthology.org/2022.deelio-1.10.pdf)
- [LLM Reasoning](https://github.com/atfortes/Awesome-LLM-Reasoning)
- [Medical Note Simplification](https://pmc.ncbi.nlm.nih.gov/articles/PMC8861686/)
- [LLMs in Healthcare](https://www.nature.com/articles/s43856-023-00370-1)

## Notes on Licensing

This project currently has no license, meaning all rights are reserved by the author. If you wish to use, modify, or distribute the code, please contact the author for permission. A license may be added in the future to clarify usage terms.

## Contact

For questions or feedback, open an issue in this repository.
