"# Short Answer Questions" 


### Q1: Explain the primary differences between TensorFlow and PyTorch. When would you choose one over the other?

**TensorFlow** is a deep learning framework developed by Google, known for its production-readiness, scalability, and robust tooling (like TensorBoard and TFLite). It supports both static and dynamic computation graphs (via `tf.function` and `eager execution`).

**PyTorch**, developed by Facebook, is beloved for its ease of use, Python based syntax, and dynamic computation graphs—making it ideal for rapid research and prototyping.

**Choose TensorFlow** when:
- You need deployment on mobile, edge, or production-scale systems.
- You're working with tools like TensorFlow Lite (For Mobile & Edge Devices) or TensorFlow Serving (For Scalable Model Serving in Production)

**Choose PyTorch** when:
- You're doing research or experimentation.  ( If you want to test a model that changes structure depending on the input (like a recursive neural network or variable-length attention model), PyTorch lets you write normal Python code with if statements and loops.)
  
- You want intuitive debugging with standard Python tools. (This makes it easy to trace errors, understand what’s going wrong, and inspect variables at any point during execution.)

---

### Q2: Describe two use cases for Jupyter Notebooks in AI development.

1. **Experimentation & Prototyping**  
   Jupyter Notebooks allow data scientists to test models and iterate quickly. You can run code in small cells, visualize outputs, and tweak parameters without rerunning the whole script.

2. **Reporting & Documentation**  
   You can combine code, plots, math (with LaTeX), and explanations in one file, making Jupyter Notebooks ideal for sharing results and creating reproducible research.

---

### Q3: How does spaCy enhance NLP tasks compared to basic Python string operations?

Basic Python string methods (`split`, `replace`, etc.) are limited to pattern-matching without understanding linguistic context.

**spaCy**, on the other hand:
- Performs tokenization with language rules.
- Recognizes parts of speech, named entities, and syntactic structure.
- Handles complex tasks like NER, lemmatization, and dependency parsing with high accuracy and speed.

It’s ideal for real-world NLP applications where context matters.

