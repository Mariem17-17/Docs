## Philosophy of the exercise
We strongly advise you to read all the document before you start to implement anything. Some questions can be answered independently, so don't hesitate to move on to the next question if you can't answer one of them. If you are unsure about an answer it's fine to skip it and discuss it during the follow-up interview.

Using ChatGPT to give you ideas is fine, but you will be asked to explain your answers. Be sure to understand them!

The following is a set of coding exercises in PyTorch based on a research paper. There are no golden answers, and hopefully, there will be no ready-to-copy answers on the web either. Note that work-in-progress implementations written in other frameworks may exist on GitHub. Being the paper recent, we don't suggest using them as a reference.


You can submit your answers in Python with a Markdown file on the side, and we'll discuss them in a follow-up interview.

Good luck from the Pulse Audition Team, and have fun! 


## Context

- Efficient sequence modeling is at the core our our research for better speech enhancement. We would like to explore the benefits of self-attention mechanisms while facing the limited resources of an embedded platform.
- (Attention as RNN)[https://arxiv.org/pdf/2405.13956] propose an alternative way to compute self-attention. The implementation we refer to in the exercise is described with a block diagram in Section 3.1 Fig. 2.
- Theoretical background can be found in Section 2.

## Questions

- The paper explains a possible way to avoid numerical issues in an implementation. Can you describe other possible numerical instabilities you can encounter together with a solution?
- Can you describe the advantages and disadvantages of the standard vs RNN implementation of self-attention? Which one would be more suitable for a memory-constrained embedded system?
- Given the Attention’s RNN Cell of Fig. 2, how can you use the cell to implement self-attention?

## Code exercise

- Provide an implementation of the block diagram for Attention’s RNN Cell of Fig. 2.
- The class you need to implement should derive from `torch.nn.Module` implementing the forward method.
- Provide a non-iterative implementation of the cell as described by the following formula for computing O_N at Section 3.1.
- Generate some dummy input and compute the absolute and relative error between the iterative and non-iterative implementations.
- Export in ONNX both implementations.

**Notes:** 

- Please provide the shapes of each input and outut Tensor in the forward method through a docstring.
- If you are uncertain on how to implement the non-iterative version, you can skip the question and provide an example usage of
the attention cell with dummy input instead of the test on relative and absolute error. You can also provide a single ONNX export for the iterative implementation in that case.
