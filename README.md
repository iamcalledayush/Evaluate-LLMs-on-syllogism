### LogiSphere: An Interdisciplinary Syllogism Dataset for LLM Evaluation


#### Summary:
- **Objective**: Developed a custom dataset named "LogiSphere" to test logical reasoning capabilities, particularly syllogistic reasoning, of various large language models (LLMs).
- **Scope**: Test syllogistic reasoning abilities of different LLMs (e.g., GPT-2 series, GPT-3.5, GPT-Neo, T5) using a custom benchmark dataset across diverse topics such as Technology, Science, Mathematics, AI/ML, Sports, and Ethics.
- **Dataset**:
  - **Structure**: Contains a total of 105 syllogism examples.
    - **100 main examples** divided across seven distinct fields: Basic Syllogism, Technology, Science, Mathematics, AI/ML, Sports, and Ethics.
    - **5 additional examples** included for K-shot prompting, allowing models to understand the format and workflow of the dataset before evaluation.
  - **Content**:
    - Each example follows a **2 Premises + 1 Conclusion** format:
      - **Premise 1** and **Premise 2** are input premises.
      - **Conclusion** is generated based on the given premises.
    - Examples are handcrafted and cover diverse real-world topics and ethical considerations, making LogiSphere a comprehensive benchmark for logical reasoning.
  - **Field Descriptions**:
    - **Basic Syllogism**: 10 generic syllogism examples.
    - **Technology**: 12 technology-related syllogisms, e.g., about adaptive learning algorithms in smart home systems.
    - **Science**: 12 science-based examples covering chemistry, biology, and physics.
    - **Mathematics**: 12 syllogisms based on mathematical principles and equations.
    - **Artificial Intelligence/Machine Learning**: 24 examples covering topics like Neural Networks, Reinforcement Learning, GANs, etc.
    - **Sports**: 20 examples related to sports like Cricket and Soccer.
    - **Ethics**: 10 examples to test ethical biases and responses of LLMs.

#### Models Evaluated:
- **GPT-2 Small, Large, XL**
- **GPT-Neo**
- **T5 Large**
- **GPT-3.5**

#### Experiments:
- **Evaluation Methods**:
  - **True/False Approach**: The model evaluates whether the conclusion follows logically from the given premises.
  - **Conclusion Output Approach**: The model generates the conclusion based on two premises provided.

#### Results:
- **Performance of Models**:
  - **Best Performance**: GPT-3.5 with an accuracy of 63%.
  - **Other Models**:
    - GPT-Neo: 47% accuracy.
    - GPT-2 XL: 24% accuracy.
    - GPT-2 Large: 19% accuracy.
    - GPT-2 Small: 10% accuracy.
  - T5 Large showed many hallucinations and was excluded from final accuracy results.

- **Key Observations**:
  - Models showed varying degrees of pattern learning based on K-shot examples, and some struggled with conclusion formulation.
  - Smaller models like GPT-2 often repeated premises or inferred incorrect conclusions, highlighting the need for larger models for better logical reasoning.

#### Technical Implementation:
- **Libraries & Tools**:
  - `transformers` for utilizing GPT-2 and T5 models.
  - `torch` for GPU-based tensor operations.
  - `pandas` for data manipulation.
  - Regular expressions (`re`) for text extraction and filtering.

- **Approach**:
  - Used 5-shot and 2-shot prompts to train and test models on the given syllogism dataset.
  - Implemented a workflow to tokenize, predict, and evaluate model outputs.
  - Processed raw outputs to check consistency with the expected conclusions and handle cases like incomplete responses.

- **Code Functions**:
  - **Output Storage**: Results saved as CSV files after model evaluation, including generated outputs for further analysis.

#### Conclusion:
- The project demonstrates how syllogistic reasoning can be effectively used to benchmark LLMs' logical abilities. Increasing model size leads to better reasoning capabilities, as observed with GPT-3.5 performing the best on LogiSphere.
- GPT 3.5 performed the best (0.63 accuracy), followed by, GPT-Neo (0.47 accuracy), GPT-XL (0.24 accuracy), GPT-2 Large (0.19 accuracy), and GPT-2 Small (0.1 accuracy).
The key takeaways from this experiment are as follows:
- The SOTA (State Of The Art) models are so powerful that we sometimes forget that models like GPT-2, which are also really powerful, struggle with tasks such as syllogism and syllogistic reasoning, which may seem simple to humans and models like GPT-4, Claude 3 Opus.
- I believe Logical Reasoning is a key area to test the Large Language Models with tasks like Syllogisms and Syllogistic Reasoning. There should be more such benchmarks which test the LLMs on their Logical Reasoning abilities in different areas of Reasoning.
