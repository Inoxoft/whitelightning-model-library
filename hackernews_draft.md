# Hacker News Draft: WhiteLightning

## Title
**Show HN: WhiteLightning – Distill massive LLMs into lightweight ONNX text classifiers**

## Post Content

Hey HN! 👋

I built **WhiteLightning** - a tool that takes massive language models (GPT-4, Claude, etc.) and distills them into ultra-lightweight text classifiers that run anywhere.

**The Problem:** You need a spam filter, sentiment analyzer, or content moderator, but don't want to hit APIs constantly or run massive models in production.

**The Solution:** WhiteLightning uses large "teacher" models to generate training data and train tiny "student" models. Think of it as going from a complex distillery to pure, potent whiskey.

## Key Features:
- **One-liner training**: Just describe what you want to classify
- **ONNX export**: Run your models in Python, JavaScript, C++, Rust, Java, Swift - basically anywhere
- **Tiny footprint**: Models are KB, not GB
- **Zero dependencies**: No TensorFlow/PyTorch needed in production
- **Multilingual**: Generate classifiers in any language

## Quick Example:
```bash
docker run --rm -v $(pwd):/app/models \
  -e OPEN_ROUTER_API_KEY="your_key" \
  ghcr.io/whitelightning-ai/whitelightning:latest \
  -p="Classify customer feedback as positive or negative"
```

That's it! You get a complete ONNX model + training data + vocab files.

## Real-World Applications:
- **Spam Detection**: `"Classify emails as spam or legitimate"`
- **Content Moderation**: `"Detect toxic vs safe user comments"`
- **Support Tickets**: `"Categorize urgency as high, medium, or low"`
- **Intent Recognition**: `"Classify user intent as booking, support, or info"`

## What Makes This Different:
Most solutions either require expensive API calls or massive model deployments. WhiteLightning gives you the best of both worlds - LLM-quality training with edge-device performance.

I've also created a **model library** where you can upload/download pre-trained classifiers: https://github.com/your-username/whitelightning-model-library

**Try it out:** https://github.com/whitelightning-ai/whitelightning

## About Us:
We're **two developers from Ukraine** - **Volodymyr Paranyak** and **Volodymyr Kyba**. Yes, we're both Volodymyrs! 😄 

Together we've been working on making advanced machine learning more accessible to developers who need practical, deployable solutions without the complexity of managing massive models.

🇺🇦 Building from Ukraine, solving problems globally.

**Connect with us:**
- Volodymyr Paranyak: [LinkedIn](https://www.linkedin.com/in/volodymyr-paranyak-978571193/)
- Volodymyr Kyba: [LinkedIn](https://www.linkedin.com/in/volodymyr-kyba-b69314180/)

Would love to hear your thoughts! What classification tasks would you tackle with this?

---

## Additional Context for Comments:

**Technical Details:**
- Uses knowledge distillation with synthetic data generation
- TF-IDF + logistic regression for the student models (surprisingly effective!)
- ONNX Runtime for inference (works everywhere)
- Teacher models generate diverse, challenging training examples
- Built-in cross-validation and edge case testing

**Inspiration:**
I got tired of choosing between "call expensive APIs forever" or "deploy 7GB models." There's a sweet spot where you get 90% of the accuracy with 0.1% of the computational cost.

**Roadmap:**
- GUI interface for non-technical users
- More architecture options (neural networks, transformers)
- Pre-trained model marketplace
- Integration with popular ML platforms

**Business Model:**
Open source (GPLv3) with potential hosted training service for enterprise users who don't want to manage their own infrastructure.

---

## Engagement Hooks:
- "I replaced a $500/month API bill with a 2MB model file"
- "This runs on a Raspberry Pi and classifies 10k messages/second"
- "From idea to production-ready classifier in 5 minutes" 