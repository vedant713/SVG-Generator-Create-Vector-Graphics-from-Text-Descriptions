# SVG-Generator

Generate SVG graphics from text descriptions with both template-based and AI-powered approaches.

## 🌟 Features

- **Template Engine:** Generate common shapes and objects with simple text commands
- **LLM Integration:** Create complex, custom vector graphics using AI (optional)
- **Color Recognition:** Automatically detects and applies colors mentioned in prompts
- **Local Processing:** Works completely offline, no API keys needed
- **Interactive Mode:** Generate SVGs on-demand with live text prompts
- **Flexible Output:** Save SVGs to files or integrate with other applications

## 📋 Requirements

### Basic Version (Template-Based)
- Python 3.8 or higher
- No special hardware required

### Advanced Version (AI-Powered)
- Python 3.8 or higher
- For Gemma 2-9B: NVIDIA GPU with 16GB+ VRAM recommended
- For Phi-2: NVIDIA GPU with 8GB+ VRAM recommended
- CPU-only operation possible but significantly slower

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/vedant713/svg-generator.git
   cd svg-generator
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   # On Windows
   venv\Scripts\activate
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   
   For template-based version (lightweight):
   ```bash
   pip install -r requirements-basic.txt
   ```
   
   For AI-powered version:
   ```bash
   pip install -r requirements-advanced.txt
   ```

4. **Setup for AI version only**
   
   If using the AI-powered version, you'll need to log in to Hugging Face:
   ```bash
   huggingface-cli login
   ```
   Then follow the prompts to enter your Hugging Face token.

## 🎮 Usage

### Command Line

1. **Template-Based Generation**
   ```bash
   python svg_generator.py "a red circle"
   ```

2. **AI-Powered Generation**
   ```bash
   python svg_generator_llm.py "a landscape with mountains and a sun"
   ```

3. **Interactive Mode**
   ```bash
   python svg_generator.py --interactive
   ```

### Python API

```python
# Template-based
from svg_generator import SVGGenerator

generator = SVGGenerator()
svg_code = generator.predict("a blue square")
generator.save_svg("a blue square", output_folder="my_svgs")

# AI-powered
from svg_generator_llm import SVGGeneratorLLM

# Use small_model=True for Phi-2, False for Gemma 2-9B
llm_generator = SVGGeneratorLLM(use_small_model=True)
svg_code = llm_generator.predict("a cartoon robot")
llm_generator.save_svg("a cartoon robot", output_folder="my_llm_svgs")
```

## 🖼️ Examples

Here are some examples of SVGs you can generate:

1. **Basic Shapes**
   - "a red circle"
   - "a blue square"
   - "a green triangle"
   - "a yellow star"

2. **Complex Descriptions** (AI version)
   - "a mountain landscape with a lake and sun"
   - "a cartoon face with a happy expression"
   - "a simple house with a tree next to it"
   - "a flower with six petals and a yellow center"

## 🔧 Customization

### Adding New Templates

You can add your own templates by modifying the `_load_templates` method in `SVGGenerator` class:

```python
def _load_templates(self) -> Dict[str, str]:
    return {
        "your_template_name": """
            <your SVG code here with {placeholders} for dynamic content>
        """,
        # Add more templates...
    }
```

### Customizing LLM Settings

For the AI-powered version, you can adjust generation parameters:

```python
outputs = self.model.generate(
    **inputs,
    max_new_tokens=1500,  # Adjust token length
    temperature=0.7,      # Adjust creativity (0.0-1.0)
    do_sample=True
)
```

## 🛡️ License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙋 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
