# SVG-Generator

A Jupyter Notebook for generating SVG graphics from text descriptions using both template-based and AI-powered approaches. Perfect for exploring SVG generation and participating in the "Drawing with LLMs" Kaggle competition.

## 🌟 Overview

This notebook provides an interactive environment for creating vector graphics from simple text prompts. Choose between a lightweight template-based approach or harness the power of language models for more complex imagery.

Originally inspired by the Kaggle "Drawing with LLMs" competition, which challenges participants to build models that generate SVG images from text descriptions, this notebook offers a starting point for those participating in the competition or anyone interested in text-to-SVG generation.

## 📋 Requirements

### For running locally:
- Python 3.8+
- Jupyter Notebook or JupyterLab
- For AI version: NVIDIA GPU with 8GB+ VRAM (recommended)

### For running on Google Colab:
- Google account
- For AI version: GPU runtime enabled (Settings → Hardware accelerator → GPU)

### For Kaggle Competition:
- Kaggle account
- Familiarity with Kaggle Packages (for competition submission)

## 🚀 Getting Started

### Option 1: Running locally

1. **Clone the repository**
   ```bash
   git clone https://github.com/vedant713/SVG-Generator-Create-Vector-Graphics-from-Text-Descriptions.git
   cd SVG-Generator-Create-Vector-Graphics-from-Text-Descriptions
   ```

2. **Set up environment**
   ```bash
   # Create and activate a virtual environment
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   
   # Install Jupyter and dependencies
   pip install jupyter
   pip install ipython
   
   # For AI version, also run:
   pip install torch transformers huggingface_hub
   ```

3. **Launch Jupyter**
   ```bash
   jupyter notebook
   ```

4. **Open the notebook**
   - Navigate to `SVG-Generator.ipynb` in Jupyter's file browser

### Option 2: Running on Google Colab

1. Open this link: [SVG-Generator on Colab](https://colab.research.google.com/github/yourusername/svg-generator/blob/main/SVG-Generator.ipynb)
2. For AI model: Enable GPU (Runtime → Change runtime type → Hardware accelerator → GPU)
3. Run the cells in order

### Option 3: Running on Kaggle

1. Go to the [Drawing with LLMs competition](https://www.kaggle.com/competitions/drawing-with-llms)
2. Fork this notebook to your Kaggle account
3. Run all cells to explore the model
4. Follow competition submission guidelines when ready

## 📒 Notebook Structure

The notebook is organized into these main sections:

1. **Setup** - Install dependencies and import libraries
2. **Template-Based Generation** - Simple approach using predefined templates
3. **AI-Powered Generation** - Advanced approach using language models
4. **Interactive Demo** - UI elements for creating SVGs with your own prompts
5. **Examples** - Showcase of generated SVGs
6. **SVG Editing** - Optional tools for modifying generated SVGs
7. **Export Tools** - Functions for saving SVGs to files
8. **Kaggle Competition** - Special section for competition participants with guidance on submission format

## 🎮 Usage Instructions

### Running the notebook

1. Execute each cell in order by clicking the ▶️ button or pressing Shift+Enter
2. Wait for the setup cells to complete before proceeding
3. For the AI version, you may need to authenticate with Hugging Face when prompted

### Generating SVGs

The notebook provides two interactive methods:

1. **Using Code Cells**:
   ```python
   # Template-based generation
   generator = SVGGenerator()
   svg_code = generator.predict("a red circle")
   display(SVG(svg_code))
   
   # AI-powered generation (if enabled)
   llm_generator = SVGGeneratorLLM(use_small_model=True)
   svg_code = llm_generator.predict("a mountain landscape")
   display(SVG(svg_code))
   ```

2. **Using Interactive Widgets** (in the demo section):
   - Type your prompt in the text input
   - Select generation method (template or AI)
   - Click "Generate SVG" button
   - View and download the result

### Kaggle Competition Integration

The notebook includes features specifically for the "Drawing with LLMs" competition:
- SVG validation against competition constraints
- Proper formatting for competition submission
- Example prompts similar to competition test cases
- Performance optimization options to meet competition requirements

## 🖼️ Example Prompts

Try these example prompts in the notebook:

### Template-based:
- "a red circle"
- "a blue square"
- "a green triangle"
- "a yellow star"
- "a purple heart"

### AI-powered:
- "a mountain landscape with a lake and sun"
- "a cartoon face with a happy expression"
- "a simple house with a tree next to it"
- "a flower with six petals and a yellow center"

## 💾 Saving Your Work

There are three ways to save generated SVGs:

1. **Within the notebook**: Generated SVGs are saved to variables
2. **Download directly**: Use the download buttons in the interactive demo
3. **Export to files**: Run the export cells to save SVGs to your local machine

## 🔄 Modifying the Notebook

Feel free to modify the notebook to suit your needs:

- Add new templates for additional shapes
- Adjust model parameters for different generation styles
- Create new cells for your own experiments
- Integrate with other visualization tools

## 🛡️ License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙋 Contributing

Contributions are welcome! Please feel free to submit a Pull Request with improvements or bug fixes.
