In the current GPU world, Deep learning models either in Computer vision or Natural language processing require lot more GPUs to run/infer on the Data.

It is most of times, important to control/limit the GPU usage. here is the sample snippet that we can use to kill the process running in GPU:

```python
# remove memory taking variables
del model
del tensor

# List all PyTorch tensors and their sizes currently allocated on GPU
print(torch.cuda.memory_summary())
print(torch.cuda.memory_allocated())
print(torch.cuda.memory_reserved())

ray.shutdown()
gc.collect()
torch.cuda.empty_cache()
```