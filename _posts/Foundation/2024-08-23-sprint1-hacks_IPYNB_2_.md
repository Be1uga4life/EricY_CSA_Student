---
layout: post
title: Sprint 1 - Objectives
description: Tools and Software Development for Sprint 1
type: issues
comments: True
---

### Creating Emojis


```python
#pip install emoji
```


```python
from emoji import emojize

emoji_dict = {
    "happy": ":grinning_face:",
    "love": ":red_heart:",
    "sun": ":sun:",
    "cat": ":cat_face:",
    "dog": ":dog_face:",
    "fire": ":fire:",
    "party": ":party_popper:",
    "thumbs up": ":thumbs_up:",
    "coffee": ":hot_beverage:"
}

def emojify_message(message):
    words = message.split()
    appended_emojis = []
    
    for word in words:
        emoji = emoji_dict.get(word.lower())
        if emoji:
            appended_emojis.append(emojize(emoji))
    
    return f"{message} {' '.join(appended_emojis)}"

message = input("Enter your message: ")

emojified_message = emojify_message(message)
print(f"{emojified_message}")

```

    i love coffee ❤️ ☕


## Extracting data


```python
# pip3 install newspaper3k
# pip3 install lxml.html.clean
```


```python
from newspaper import Article
from IPython.display import display, Markdown


urls = ["https://www.ibm.com/topics/neural-networks"]

for url in urls:
    article = Article(url)
    article.download()
    article.parse()

    display(Markdown("### Summary"))
    display(Markdown(article.summary))
    
    display(Markdown(article.title)) 
    display(Markdown(article.text)) 
    print("\n")

```


### Summary







What is a Neural Network?



Think of each individual node as its own linear regression model, composed of input data, weights, a bias (or threshold), and an output. The formula would look something like this:

∑wixi + bias = w1x1 + w2x2 + w3x3 + bias

output = f(x) = 1 if ∑w1x1 + b>= 0; 0 if ∑w1x1 + b < 0

Once an input layer is determined, weights are assigned. These weights help determine the importance of any given variable, with larger ones contributing more significantly to the output compared to other inputs. All inputs are then multiplied by their respective weights and then summed. Afterward, the output is passed through an activation function, which determines the output. If that output exceeds a given threshold, it “fires” (or activates) the node, passing data to the next layer in the network. This results in the output of one node becoming in the input of the next node. This process of passing data from one layer to the next layer defines this neural network as a feedforward network.

Let’s break down what one single node might look like using binary values. We can apply this concept to a more tangible example, like whether you should go surfing (Yes: 1, No: 0). The decision to go or not to go is our predicted outcome, or y-hat. Let’s assume that there are three factors influencing your decision-making:

Are the waves good? (Yes: 1, No: 0) Is the line-up empty? (Yes: 1, No: 0) Has there been a recent shark attack? (Yes: 0, No: 1)

Then, let’s assume the following, giving us the following inputs:

X1 = 1, since the waves are pumping

X2 = 0, since the crowds are out

X3 = 1, since there hasn’t been a recent shark attack

Now, we need to assign some weights to determine importance. Larger weights signify that particular variables are of greater importance to the decision or outcome.

W1 = 5, since large swells don’t come around often

W2 = 2, since you’re used to the crowds

W3 = 4, since you have a fear of sharks

Finally, we’ll also assume a threshold value of 3, which would translate to a bias value of –3. With all the various inputs, we can start to plug in values into the formula to get the desired output.

Y-hat = (1*5) + (0*2) + (1*4) – 3 = 6

If we use the activation function from the beginning of this section, we can determine that the output of this node would be 1, since 6 is greater than 0. In this instance, you would go surfing; but if we adjust the weights or the threshold, we can achieve different outcomes from the model. When we observe one decision, like in the above example, we can see how a neural network could make increasingly complex decisions depending on the output of previous decisions or layers.

In the example above, we used perceptrons to illustrate some of the mathematics at play here, but neural networks leverage sigmoid neurons, which are distinguished by having values between 0 and 1. Since neural networks behave similarly to decision trees, cascading data from one node to another, having x values between 0 and 1 will reduce the impact of any given change of a single variable on the output of any given node, and subsequently, the output of the neural network.

As we start to think about more practical use cases for neural networks, like image recognition or classification, we’ll leverage supervised learning, or labeled datasets, to train the algorithm. As we train the model, we’ll want to evaluate its accuracy using a cost (or loss) function. This is also commonly referred to as the mean squared error (MSE). In the equation below,

i represents the index of the sample,

y-hat is the predicted outcome,

y is the actual value, and

m is the number of samples.

𝐶𝑜𝑠𝑡 𝐹𝑢𝑛𝑐𝑡𝑖𝑜𝑛= 𝑀𝑆𝐸=1/2𝑚 ∑129_(𝑖=1)^𝑚▒(𝑦 ̂^((𝑖) )−𝑦^((𝑖) ) )^2

Ultimately, the goal is to minimize our cost function to ensure correctness of fit for any given observation. As the model adjusts its weights and bias, it uses the cost function and reinforcement learning to reach the point of convergence, or the local minimum. The process in which the algorithm adjusts its weights is through gradient descent, allowing the model to determine the direction to take to reduce errors (or minimize the cost function). With each training example, the parameters of the model adjust to gradually converge at the minimum.

See this IBM Developer article for a deeper explanation of the quantitative concepts involved in neural networks.

Most deep neural networks are feedforward, meaning they flow in one direction only, from input to output. However, you can also train your model through backpropagation; that is, move in the opposite direction from output to input. Backpropagation allows us to calculate and attribute the error associated with each neuron, allowing us to adjust and fit the parameters of the model(s) appropriately.


    
    

