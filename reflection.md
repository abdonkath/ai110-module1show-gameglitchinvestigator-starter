# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").

The program is saying lower when I entered the number but the correct number is higher than my guess.

When I press new game the correct number changed but I couldn't input anything on the line.

The first guess is not recording in history. The range of easy, medium, and hard is incorect

The attempts left does not decrement on the first guess

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

I used Claude. One suggestion that was correct was the range of each mode. AI was able to correctly point out which part were the ranges in the code and fixed them to correct range. One misleading was when the first guess is not recording in history, AI was suggesting that the issue was how the history was being appended. However, the real problem was history was being updated from starting index 0 after second guess, the first guess was never added.

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

I decided whether the bug was really fixed by trrying the app itself, in each mode, multiple times and looking at the code itself after. I ran manual test by starting new game, and entering first guess, and checking where it will appear in history. The history was empty and only starts appedning on second guess. This showed me that the history update logic was being skipped on the first try.

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

Looking at this question, I did not notice that the secret number was changing at all. So, I tried testing streamlit to see for myself. It was not changing for me, the secret number stayed the same the whole game. It is possible AI fixed it without me noticing, I will keep this in mind next time.

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
   - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

For prompting strategy, I think longer and detailed prompt gives the best result. I noticed that the prompt does not have to be perfect, but if you list out the problems with details, it solves it immidiatelty. Claude has option for "Ask before edits" and "Plan mode". I tried both, and I am leaning towards plan mode because I could actually see the code that's being changed with explination. So, maybe next project I'll use plan mode mode often. This project made me realize how easy it is to debug, you could give a prompt from a user's perspective and it will fixed AI for you.
