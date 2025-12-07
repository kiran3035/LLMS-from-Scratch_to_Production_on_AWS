# Contributing to LLMs from Scratch

Thank you for your interest in contributing! This document provides guidelines for contributing to the project.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How to Contribute](#how-to-contribute)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Style Guidelines](#style-guidelines)

## 🤝 Code of Conduct

- Be respectful and inclusive
- Provide constructive feedback
- Focus on what is best for the community
- Show empathy towards other contributors

## 💡 How to Contribute

### Reporting Bugs

1. Check if the bug has already been reported in [Issues](https://github.com/yourusername/llms-from-scratch/issues)
2. If not, create a new issue with:
   - Clear title and description
   - Steps to reproduce
   - Expected vs actual behavior
   - Environment details (Python version, OS, etc.)
   - Screenshots if applicable

### Suggesting Enhancements

1. Check existing issues/discussions for similar suggestions
2. Create a new issue describing:
   - Current behavior
   - Desired behavior
   - Why this enhancement would be useful
   - Possible implementation approach

### Contributing Code

1. Fork the repository
2. Create a new branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Test thoroughly
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

## 🛠️ Development Setup

```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/llms-from-scratch.git
cd llms-from-scratch

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Install development dependencies
pip install pytest black flake8 jupyter
```

## 🔄 Pull Request Process

1. **Update Documentation**: If you change functionality, update relevant notebooks/docs
2. **Test Your Changes**: Ensure notebooks run without errors
3. **Follow Style Guidelines**: See below
4. **Update CHANGELOG**: Add a note about your changes
5. **One Feature Per PR**: Keep PRs focused on a single feature/fix

### PR Title Format

- `feat:` New feature
- `fix:` Bug fix
- `docs:` Documentation changes
- `style:` Code style/formatting
- `refactor:` Code refactoring
- `test:` Adding tests
- `chore:` Maintenance tasks

Examples:
- `feat: Add BERT tokenizer support`
- `fix: Correct attention mask calculation`
- `docs: Update AWS setup instructions`

## 📝 Style Guidelines

### Python Code

```python
# Follow PEP 8
# Use meaningful variable names
# Add docstrings to functions/classes

def calculate_perplexity(logits, targets):
    """
    Calculate perplexity metric.
    
    Args:
        logits (torch.Tensor): Model predictions
        targets (torch.Tensor): Ground truth labels
    
    Returns:
        float: Perplexity score
    """
    loss = F.cross_entropy(logits, targets)
    return torch.exp(loss).item()
```

### Jupyter Notebooks

- **Clear Cell Outputs**: Clear outputs before committing (except for example results)
- **Markdown Headers**: Use proper hierarchy (##, ###, etc.)
- **Code Comments**: Explain complex logic
- **Cell Organization**: Keep cells focused and modular

### Commit Messages

```bash
# Good
git commit -m "feat: Add LoRA adapter merging functionality"
git commit -m "fix: Resolve tokenization issue with special characters"
git commit -m "docs: Add deployment cost breakdown"

# Bad
git commit -m "update"
git commit -m "fixed stuff"
git commit -m "changes"
```

## 🧪 Testing

Before submitting a PR:

```bash
# Run notebooks sequentially
jupyter nbconvert --execute --to notebook \
    01_LLM_Fundamentals.ipynb

# Check code style
black --check .
flake8 .

# Test AWS cleanup script
python aws_cleanup.py --dry-run
```

## 📚 Documentation

- Update README.md if you add new features
- Update relevant notebook markdown cells
- Add examples for new functionality
- Update INDEX.md if you add new notebooks

## 🎯 Good First Issues

Look for issues labeled:
- `good first issue`
- `documentation`
- `help wanted`

## 💬 Questions?

- Open a [Discussion](https://github.com/yourusername/llms-from-scratch/discussions)
- Ask in [Issues](https://github.com/yourusername/llms-from-scratch/issues)

## 🙏 Thank You!

Your contributions make this project better for everyone. We appreciate your time and effort!

---

**Happy Contributing!** 🚀

