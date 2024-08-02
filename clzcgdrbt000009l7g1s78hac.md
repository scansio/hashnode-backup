---
title: "My Turing Challenge Experience: A Lesson in Humility and Problem-Solving"
seoTitle: "Turing Challenge: Longest Subsequence"
seoDescription: "A coder's journey through failure, learning humility, and finding simpler problem-solving methods in the Turing Challenge"
datePublished: Fri Aug 02 2024 08:38:57 GMT+0000 (Coordinated Universal Time)
cuid: clzcgdrbt000009l7g1s78hac
slug: my-turing-challenge-experience-a-lesson-in-humility-and-problem-solving
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1722586188261/4d66878d-1b26-49a6-bc7d-5294ae4b2bd4.png
tags: coding-challenge, data-structure-and-algorithms, turing, turing-test, longest-subsequence-problem

---

Have you ever felt the sting of failure when you least expected it? That's exactly what happened to me during the Turing Challenge. Let me take you through my journey of overconfidence, failure, and ultimately, growth.

#### The Problem That Humbled Me: Longest Subsequence

Picture this: You're sitting in front of your computer, fingers poised over the keyboard, ready to tackle any coding challenge thrown your way. That was me, brimming with confidence as I started the Turing Challenge. The problem seemed simple enough:

> Given an array of 0s and 1s, return the length of the longest subsequence. A subsequence is a series of adjacent elements where no two adjacent elements are the same.

**Examples:**

* Input: `[0, 1, 0, 1, 0]` → Output: `5`
    
* Input: `[0]` → Output: `1`
    

Simple, right? Well, I thought so too. But oh, how wrong I was.

#### The Fall: My Overcomplicated Solution

In my hubris, I dove into crafting what I thought was a clever, sophisticated solution. I created dictionaries, nested conditions, and even threw in some fancy iteration techniques. Here's a glimpse of my initial attempt:

```python
def longestSubSequence(X:list[int]):
    """Approach 

    1. Iterate through the list and extract the length of subsequences into a dictionary
    input: [0, 1, 0, 1, 0, 0, 1, 1]
    output: {0: 5, 1: 2, 3: 1}

    2. Iterate the dictionary and return the max of dictionary values
    input: {0: 5, 1: 2, 3: 1}
    output: 5
    """

    dict = {}

    length = len(X)
    sub = 0
    i = 0

    while i < length:
        centerItem = X[i]
        rightItem = None

        if (i + 1) < length:
            rightItem = X[i + 1]
        
        if (centerItem == 0 and (rightItem == 1 or rightItem == None)) or (centerItem == 1 and (rightItem == 0 or rightItem == None)):
            if (rightItem == None):
                dict[sub] = (dict.get(sub) or 0) + 1
            else:
                dict[sub] = (dict.get(sub) or 0) + 2
            
            #We compare two items on every iteration
            i += 2
        else:
            sub = i
            i += 1

    count = -1

    for value in dict.values():
        if value > count:
            count = value

    return count

#Driver code        
if __name__ == '__main__':
    A = [
        [0], #Output: 1
        [0, 0], #Output: 1
        [1, 0], #Output: 2
        [1, 1], #Output: 1
        [0, 1, 0, 1, 1], #Output: 4
        [0, 1, 0, 1, 0], #Output: 5
        [0, 1, 0, 1, 0, 0], #Output: 5
        [1, 1, 0, 1, 0] #Output: 4
        ]
    for arr in A:
        print("Array: ", arr)
        print("Result: ", longestSubSequence(arr))
```

I was so proud of this solution. I thought I had cracked it wide open. But when I submitted it, reality hit hard. Only 30% of the test cases passed. The rest? Failed spectacularly.

#### The Aftermath: Anger, Frustration, and a Dash of Embarrassment

I won't lie – I was furious. How could such a simple problem bring me down? It felt like a personal affront to my coding skills. But as the anger subsided, embarrassment crept in. Had I really overcomplicated such a straightforward task?

#### Rising from the Ashes: A Simpler Approach

After the test, with my ego bruised but my determination intact, I sat down to debug my code. And that's when it hit me – I had been trying to swat a fly with a sledgehammer. The solution didn't need all those bells and whistles. Here's what I came up with after some reflection:

```python
def longestSubSequence(X:list[int]):
    """Approach 
    1. Iterate through the list and extract the length of subsequences into a dictionary
    input: [0, 1, 0, 1, 0]
    output: {0: 5}

    2. Iterate the dictionary and return the max of dictionary values
    input: {0: 5}
    output: 5
    """

    dict = {}

    length = len(X)
    sub = 0
    i = 0

    previousItem = None

    while i < length:
        centerItem = X[i]
        
        if centerItem == previousItem:
            sub = i
        
        dict[sub] = (dict.get(sub) or 0) + 1
        previousItem = centerItem
        i += 1

    count = -1

    for value in dict.values():
        if value > count:
            count = value

    return count

#Driver code 
if __name__ == '__main__':
    A = [
        [0], #Output: 1
        [0, 0], #Output: 1
        [1, 0], #Output: 2
        [1, 1], #Output: 1
        [0, 1, 0, 1, 1], #Output: 4
        [0, 1, 0, 1, 0], #Output: 5
        [0, 1, 0, 1, 0, 0], #Output: 5
        [1, 1, 0, 1, 0] #Output: 4
        ]
    for arr in A:
        print("Array: ", arr)
        print("Result: ", longestSubSequence(arr))
```

This version, though I didn't get it tested using Turing public/hidden test, while not perfect, was a significant improvement. It was cleaner, more straightforward, and most importantly, it worked better.

#### The Lessons Learned

1. **Simplicity is key:** Sometimes, the most elegant solution is the simplest one.
    
2. **Check your ego at the door:** Overconfidence can be your worst enemy in problem-solving.
    
3. **Step back when stuck:** A fresh perspective can work wonders.
    
4. **Embrace failure as a teacher:** Every mistake is an opportunity to learn and grow.
    

#### Moving Forward: A Humbler, Wiser Coder

This experience was a wake-up call. It reminded me that in the world of coding, there's always more to learn. No matter how experienced you think you are, staying humble and open to learning is crucial.

#### Your Turn

Have you ever faced a similar situation? How do you deal with coding setbacks? Share your experiences in the comments – let's learn from each other!

And remember, if you're ever stuck on a problem, don't hesitate to reach out. Sometimes, a fresh pair of eyes is all you need to crack that tough nut.

**Let's connect:**

* Email: [scansioquielom@gmail.com](mailto:scansioquielom@gmail.com)
    
* WhatsApp: +2349074395694
    
* X (Twitter): [@elom\_emmanuel7](https://x.com/elom_emmanuel7)
    
* LinkedIn: [Scansio](https://www.linkedin.com/in/scansio/)
    

Don't forget to like, comment, and follow for more real-talk coding experiences. Together, we can turn our failures into stepping stones to success!