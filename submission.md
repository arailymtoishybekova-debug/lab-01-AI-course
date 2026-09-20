# Lab 01 – The Price of One Request

## 1. Prediction and Results

Before running the API, I tried to predict how many tokens Russian and Kazakh could use compared to English. I used the byte size from Part 1.

For the complaint, English had 300 bytes, Russian had 576 bytes and Kazakh had 640 bytes. Based on this, my prediction was:

- Russian / English = 1.92x
- Kazakh / English = 2.13x

Then I tested the same task using Gemini 3.6 Flash. I got 628 output tokens for English, 1,155 for Russian and 1,635 for Kazakh.

The real ratios were:

- Russian / English = 1.84x
- Kazakh / English = 2.60x

For Russian my prediction was quite close. For Kazakh the difference was bigger than I expected. From this experiment I understood that the size of the text in bytes and the number of tokens are related, but they are not the same thing.

## 2. Annual Cost

For my calculation I chose 5,000 requests per day. I think this is a reasonable example for a support service that receives many requests every day.

| Language | Input tokens | Output tokens | Annual cost |
|---|---:|---:|---:|
| English | 60 | 628 | $4,380.00 |
| Russian | 79 | 1,155 | $8,012.66 |
| Kazakh | 149 | 1,635 | $11,393.47 |

The total cost for all three languages would be $23,786.14 per year if each language had 5,000 requests every day.

In my results, Kazakh was the most expensive. The main reason is that the Kazakh answer had more output tokens.

## 3. Model for Kazakh Support

In this lab I used Gemini 3.6 Flash. I would consider this type of fast model for a Kazakh support queue because support systems can have many requests and the cost of every request matters.

At the same time, I would not look only at the price. During my test, I noticed that the model sometimes added information and possible explanations that were not given in the original task. This can be a problem in real customer support.

So before using it in a real Kazakh support system, I would test more Kazakh examples and check if the answers are correct and follow the instructions. For me, both cost and quality are important for this decision.

## 4. How the Cost Could Be Reduced

One way to reduce the cost that I did not use in this lab is to limit the length of the answer. If the model gives shorter answers, it uses fewer output tokens, so each request becomes cheaper.
