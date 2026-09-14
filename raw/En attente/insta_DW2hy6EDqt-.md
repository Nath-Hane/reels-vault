---
source: https://www.instagram.com/reel/DW2hy6EDqt-/
plateforme: Instagram
genre: video
auteur: Giga Qian
duree_s: 178.33299255371094
traite_le: 2026-09-08
statut: brut
---

# Video by gigaqian

## Description
Kronos is a time series foundation model specifically designed to forecast price action in financial markets. In this video, I will teach you how it works! You’ll have a strong technical understanding for the first steps to turning financial data into a language. It’s complicated, so please ask questions if you need clarifications!

#learnai #learnoninstagram #aifinance #newai #gigaqian

## Transcription audio
I found something that shouldn't exist yesterday, and after sharing it, a lot of you asked me to explain it. So I will. I'm Giga Chen and I do business in China, a country in which a PhD student released an AI that can predict the markets, stocks, crypto, and so on, and he did it for free. I found and read the official research paper, so you don't have to, and by the end of this video, you're going to understand how this works on a near-expert level. For context, Chronos, the price-predicting AI, was created by a guy named Su Yu, who's a PhD student at Tsinghua University, which is like China's Harvard. His lab is the Institute for Interdisciplinary Information Sciences. Chronos is a time series foundation model. A time series is a sequence of data points recorded at successive time intervals, like a heart rate, or a stock chart. A foundation model seeks to generalize. That means work on data it wasn't specifically trained on, like new information in the market. So how does it work? There are five steps, an input and output, and three steps in the middle, which I am more than happy to break down. And I hope all the he's an AI fool's really enjoyed that breakdown. To build Chronos, they have to tokenize K-lines. But what does that mean? K-lines are those candlesticks you see on a chart. You have an open, and then you have a high, a low, and a close. You also have volume. Tokenization is breaking down a large, messy stream of information into small chunks called tokens. These are basically digital IDs. The classic oversimplification you might hear is that an LLM might break down talking into talk and ing, but that's not going to work for the market. A stock price isn't like a word. It's a number, which is a bigger issue than you might think. They have decimals, which means they're continuous, but we need them to be discreet. But what does it mean to be discreet anyways? I explained it more in depth in my quantum video, but discreet basically means sorted or rounded into slots with no in between. So the stock market's kind of like a continuous ramp. It's going up and down. It's wavy. Discreet makes it more like stairs. Are you going to take a step up or a step down? And to bring the knowledge back, each of those steps for Kronos is a token. In the world of AI math, you want the data to be balanced around zero. If you have ones and zeros, your average is 0.5. This makes the system slow. It's heavier. But if you have ones and negative ones, it's zero centered. The average is zero and your system moves way faster. Rather than trying to split a number like a word, Kronos projects the K-line onto a mathematical sphere, and wherever it lands on there causes the assignment of a unique digital ID. This is a string of ones, and you guessed it, negative ones. Why do this? Stock prices are all over the place. Imagine buying a penny stock and then buying a share of Berkshire Hathaway. The AI would get confused. It would go, $100 move happened in both of these. That's not the same thing. The sphere normalizes things. It's not looking at the raw dollar amounts. It's looking at the direction and the relationship of the moves. Got all that? You just nailed step one. It's called binary spherical quantization, and you can see why I waited to say it. It's scary name. It's impossible to give you the full knowledge of this kind of thing in a short video, but let me know if you're still interested and I'll cover the other steps. Otherwise, we'll move on with other stories. By the way, I implemented Kronos in one of my trading strategies today.

## Images
- images/insta_DW2hy6EDqt-_1.jpg
- images/insta_DW2hy6EDqt-_2.jpg
- images/insta_DW2hy6EDqt-_3.jpg
