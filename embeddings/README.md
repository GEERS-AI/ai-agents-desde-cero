# Multi-Lingual Embeddings

Using a embeddings model, I would like to test the following hypothesis:

```python
# Assuming you have a pre-trained embeddings model loaded as `model`

v1 = model.encode("Hello world")
v2 = model.encode("Hola mundo")

# Calculate the cosine similarity between the two vectors
similarity = cosine_similarity(v1, v2)

# Is similarity near to 1.0?
```
