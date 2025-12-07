# Quick Start Guide - LLM from Scratch

## 🚀 Get Started in 5 Minutes

### Option 1: Google Colab (Fastest, Free GPU)

1. **Click a notebook** in this repository
2. **Click the "Open in Colab" badge** at the top
3. **Run cells** sequentially (Shift+Enter or click Run button)
4. **Done!** Free GPU access included

**Recommended order:**
```
01_LLM_Fundamentals.ipynb       ← Start here (theory)
02_Text_Data_Tokenization.ipynb ← Data processing
03_Attention_Mechanisms.ipynb   ← Core algorithm
04_GPT_Model.ipynb              ← Build the model
05_Pretraining.ipynb            ← Train it
06_Classification_Finetuning.ipynb
07_Instruction_Finetuning.ipynb
```

---

### Option 2: Local Setup (5 minutes)

```bash
# 1. Clone repository
git clone <your-repo-url>
cd portfolio_project

# 2. Create virtual environment
python -m venv venv

# 3. Activate environment
# On Windows:
venv\Scripts\activate
# On Mac/Linux:
source venv/bin/activate

# 4. Install dependencies
pip install -r requirements.txt

# 5. Start Jupyter
jupyter lab

# 6. Open notebooks and run!
```

**System Requirements:**
- Python 3.8 or higher
- 8GB RAM minimum (16GB recommended)
- GPU optional (CPU works but slower)

---

### Option 3: AWS SageMaker (Production)

#### Step 1: Create SageMaker Notebook Instance

```bash
aws sagemaker create-notebook-instance \
    --notebook-instance-name llm-from-scratch \
    --instance-type ml.t3.medium \
    --role-arn arn:aws:iam::YOUR_ACCOUNT:role/SageMakerRole
```

**Or use AWS Console:**
1. Go to AWS SageMaker Console
2. Click "Notebook instances"
3. Click "Create notebook instance"
4. Name: `llm-from-scratch`
5. Instance type: `ml.t3.medium`
6. Create

#### Step 2: Open Jupyter

1. Wait for instance to be "InService"
2. Click "Open JupyterLab"
3. Clone this repository in terminal

#### Step 3: Run Notebooks

Start with `01_LLM_Fundamentals.ipynb`

**Cost**: ~$0.05/hour for development

---

## 📚 Notebook Guide

### 1️⃣ LLM Fundamentals (30 minutes)
**What you'll learn:**
- What are LLMs?
- Transformer architecture
- Training stages
- AWS cost optimization

**No coding required!** Pure concepts and visualizations.

**Key outputs:**
- Architecture diagrams
- Cost calculator
- Model comparison charts

---

### 2️⃣ Text Data & Tokenization (45 minutes)
**What you'll learn:**
- How to convert text to numbers
- Tokenization methods
- BPE algorithm
- Embeddings

**You'll build:**
- Custom BPE tokenizer
- Embedding layer
- Data loader

**Key outputs:**
- Working tokenizer
- Visualization of token distributions
- Data pipeline for training

---

### 3️⃣ Attention Mechanisms (60 minutes)
**What you'll learn:**
- Self-attention from scratch
- Query, Key, Value
- Multi-head attention
- Causal masking

**You'll implement:**
- Attention mechanism
- Multi-head version
- Complete causal attention

**Key outputs:**
- Attention visualizations
- Working multi-head attention
- Understanding of core algorithm

---

### 4️⃣ GPT Model (60 minutes)
**What you'll build:**
- Complete GPT architecture
- Layer normalization
- Feed-forward networks
- Transformer blocks

**Result:** 
Full GPT-2 model (124M parameters) ready for training!

**Key outputs:**
- Complete model code
- Text generation function
- Parameter counting

---

### 5️⃣ Pretraining (90 minutes)
**What you'll do:**
- Implement training loop
- Train the model
- Save checkpoints
- Evaluate performance

**On GPU:** ~2 hours training
**On CPU:** ~8 hours training

**Key outputs:**
- Trained model
- Loss curves
- Generated text samples

---

### 6️⃣ Classification Finetuning (45 minutes)
**What you'll do:**
- Adapt model for classification
- Train on spam detection
- Evaluate performance

**Key outputs:**
- Finetuned classifier
- Evaluation metrics
- Working classifier

---

### 7️⃣ Instruction Finetuning (45 minutes)
**What you'll do:**
- Instruction formatting
- LoRA finetuning
- Model deployment
- Inference endpoint

**Key outputs:**
- Instruction-following model
- Deployed endpoint
- REST API

---

## 🎯 Learning Paths

### Path 1: Quick Overview (2 hours)
**Goal:** Understand concepts, skip implementation details

1. Chapter 1 - Read all
2. Chapter 2 - Read theory, skip coding
3. Chapter 3 - Read theory, run code
4. Chapter 4 - Read theory, skip coding
5. Chapter 5 - Read theory, skip training
6. Chapters 6-7 - Skim

**Outcome:** Conceptual understanding of LLMs

---

### Path 2: Complete Implementation (2 days)
**Goal:** Understand and implement everything

**Day 1:**
- Morning: Chapters 1-2 (4 hours)
- Afternoon: Chapter 3 (3 hours)

**Day 2:**
- Morning: Chapter 4 (3 hours)
- Afternoon: Chapter 5 (4 hours)
- Evening: Chapters 6-7 (2 hours)

**Outcome:** Complete working knowledge + code

---

### Path 3: Portfolio Focus (1 week)
**Goal:** Build impressive portfolio project

**Days 1-2:** 
- Study chapters 1-4
- Customize code
- Add comments

**Days 3-4:**
- Train model (Chapter 5)
- Document results
- Take screenshots

**Days 5-6:**
- Finetune models (Chapters 6-7)
- Deploy endpoints
- Test inference

**Day 7:**
- Write blog post
- Create demo video
- Polish README
- Push to GitHub

**Outcome:** Professional portfolio project

---

## ⚡ Pro Tips

### For Learning
1. **Run every cell** - Don't just read
2. **Modify parameters** - See what changes
3. **Add print statements** - Understand shapes
4. **Draw diagrams** - Visualize flow
5. **Explain to someone** - Best way to learn

### For Portfolio
1. **Add your name** to all notebooks
2. **Customize visualizations** with your style
3. **Add extra experiments** (change hyperparameters)
4. **Document results** with markdown cells
5. **Create a demo video** showing it working

### For Interviews
1. **Know one notebook deeply** (prefer Ch 3 or 4)
2. **Can explain attention** without looking
3. **Understand trade-offs** (speed vs accuracy)
4. **Know AWS costs** - shows production thinking
5. **Have examples ready** - "When I implemented..."

---

## 🐛 Troubleshooting

### Issue: Out of Memory (GPU)
**Solution:**
```python
# Reduce batch size
batch_size = 2  # instead of 8

# Reduce sequence length
max_length = 128  # instead of 256

# Use gradient accumulation
accumulation_steps = 4
```

### Issue: Slow Training (CPU)
**Solution:**
- Use Google Colab free GPU
- Or reduce model size:
```python
GPT_CONFIG = {
    "n_layers": 6,  # instead of 12
    "n_heads": 6,   # instead of 12
    "emb_dim": 384  # instead of 768
}
```

### Issue: Import Errors
**Solution:**
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### Issue: AWS Credentials
**Solution:**
```bash
# Configure AWS CLI
aws configure

# Or set environment variables
export AWS_ACCESS_KEY_ID=your_key
export AWS_SECRET_ACCESS_KEY=your_secret
```

---

## 📊 Expected Results

### After Chapter 3:
- ✅ Working attention mechanism
- ✅ Attention visualizations
- ✅ Understanding of core algorithm

### After Chapter 4:
- ✅ Complete GPT model (124M params)
- ✅ Can generate text (random at first)
- ✅ Model architecture implemented

### After Chapter 5:
- ✅ Trained model
- ✅ Decreasing loss curve
- ✅ Coherent text generation

### After Chapter 6:
- ✅ Classification model
- ✅ High accuracy (>90%)
- ✅ Working spam detector

### After Chapter 7:
- ✅ Instruction-following model
- ✅ Deployed endpoint
- ✅ REST API working

---

## 🎓 Next Steps After Completion

### Immediate (Day 1)
- [ ] Push to GitHub
- [ ] Update LinkedIn
- [ ] Add to resume

### Short-term (Week 1)
- [ ] Write blog post
- [ ] Create demo video
- [ ] Share on social media

### Long-term (Month 1)
- [ ] Implement improvements
- [ ] Try larger models
- [ ] Build applications using it

---

## 💡 Common Questions

**Q: Do I need a GPU?**
A: No, but it's faster. Use Google Colab's free GPU.

**Q: How long does training take?**
A: On GPU: 2-3 hours. On CPU: 8-12 hours.

**Q: What if I get stuck?**
A: Each notebook has detailed comments. Also check PROJECT_SUMMARY.md.

**Q: Can I use this for commercial projects?**
A: Yes! MIT license allows commercial use.

**Q: How do I customize it?**
A: Change hyperparameters, add features, try different datasets.

**Q: Is this production-ready?**
A: Core code is solid. For production, add: error handling, logging, monitoring, testing.

---

## 🚀 You're Ready!

Pick your path above and start with **Chapter 1**.

**Remember:**
- Take your time
- Run every cell
- Experiment with parameters
- Document your changes
- Have fun learning!

**Questions?** Check PROJECT_SUMMARY.md for detailed information.

**Good luck! You've got this! 🎉**

