# Question-Answering-Model

The answer column in the dataset contained context for the given question from which, to extract the answer, it was summarized using the Lex Rank Summarizer from the sumy library in Python. The number of sentences in the output summary was fixed to 2, which was decided based on trial and error on different training examples.

Moving On, the Encoder-Decoder model seemed to be suitable for the aforementioned use case; the question entered generates the key and value vectors when passed through subsequent layers of the encoder, which are then fed into the decoder. 
The pre-trained T5 Text-to-Text transformer model was fine-tuned for our downstream task.

The metric used for validation was the BLEU score, which compares the generated responses to human-generated responses and outputs the comparative score.

Another approach tried was using pre-trained GPT-2, which is a decoder-only model, but the training time for that was about 13 days, which is huge for such a task.

In use cases like these, the model is required to understand the context of the questions and answers so that after training, the fine-tuned model can output the correct answers.
