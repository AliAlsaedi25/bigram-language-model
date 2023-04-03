# bigram-language-model
using torch and the gpt transformer model i was able to create a language model that will use feed forward technique as well as multi head attention, self attention, linear normality of the data and softmax as well to try and trian a model to mimic the input text it was given

here are some of the papers I read 
- Attention is All You Need paper: https://arxiv.org/abs/1706.03762
- OpenAI GPT-3 paper: https://arxiv.org/abs/2005.14165 
as well as torch documentation give that a read to undersand what I have done here 

in a sense the training loop will run in parellel on 384 pice with 6 different threads 64 per thread adn each thread will have 64 dimensions through 5000 iterations

it will first mask the data in a trilagular mask and a apply a linear normaility to make the sure the data is not averaged and not relinate on a single chachter other wise it will become too beaky i accomplished this by adding the linear norm layer as well as taking the soft max so we get smoothe rounded data 
the next step would be multi head attention where heach chachter at each head will look at the previous chachters as well as itself to tryi and predict or generate witha the next charchter should be after that you will add a it to iteselt and normilze the data with the softmax 
finally you will feedthe information forward to at every step to help the next token predict the next step and than again you guessed it linear norm and take a softmax 

im not sure if this made much sense but i tried to write very good documentation for whoever wants to follow along
