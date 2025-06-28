The rapid growth of scientific literature in all fields makes it very hard to automatically sort 
documents, especially long academic writings. BERT and other transformer-based systems work 
well on short texts, but they can only take in sequences of up to 512 tokens. This limitation makes 
it harder for them to find long-range relationships and hierarchical structure, which are very 
important for correctly classifying scientific articles. This study gets around these problems by 
using Longformer, a transformer model with a new sparse attention mechanism that lets it handle 
sequences of up to 4,096 tokens quickly while keeping the ability to scale linearly with sequence 
length. We suggest a strong document classification pipeline that looks at and compares the 
BERT-base, Longformer-base, and Longformer-large architectures on a carefully chosen subset 
of the arXiv dataset, which contains 90,000 full-text articles from the fields of Computer Science, 
Mathematics, and Physics, divided into 30 smaller subcategories. The pre-processing pipeline 
uses section-aware tokenization, truncation algorithms that keep the content of the abstract and 
introduction, and hierarchical input construction to make sure that the meaning and structure of 
the text stay the same. We used the HuggingFace Transformers framework to fine-tune each 
model and then measured how well they worked using the macro-F1 score, accuracy, and per
class precision/recall.  Longformer-large does better than both BERT-base and Longformer-base 
in practice, getting a macro-F1 score of 84.7% and making big improvements in areas where 
contextual dependencies are naturally longer. The results show that sparse attention mechanisms 
work well to improve understanding of long documents and prove that Longformer is the best 
model for classifying scholarly documents. This work also gives us more information about how 
to make transformer topologies work better for real-world NLP tasks that involve long text 
inputs. 