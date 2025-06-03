


**Reads:**
- https://docs.github.com/en/github-models/prototyping-with-ai-models
	- https://github.com/marketplace/models
- [Anthropic Cookbook](https://github.com/anthropics/anthropic-cookbook?tab=readme-ov-file): Code and guides designed to help build. 


people interacting with LLM:
- https://simonwillison.net/2025/Mar/25/gemini/

**Prompt Engineering:**
- [ ] https://www.uber.com/en-IN/blog/introducing-the-prompt-engineering-toolkit/?=&aid=recbxr9IRM7UNGV8S
- [ ] https://docs.lovable.dev/tips-tricks/prompting
- [ ] (video) [AI prompt engineering: A deep dive](https://www.youtube.com/watch?v=T9aRN5JkmL8)
- [ ] Sites:
	- [ ] Prompt Tools: https://webcurate.co/c/prompt
- [ ] Prompts:
	- [ ] https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm
	- [ ] Prompt Engineering: 
	- https://drive.google.com/file/d/1876aoMFIKbgCVuoUtRHQYRs7Kcn6SMZD/view?ref=blog.codewithahsan.dev


**Prompt Variations:**

1. **Q/A Prompt**: propose  X. Ask me a series of yes/no questions that will help you provide a better recommendation 
2. **Pros & cons Prompt**: What are a few different  ways that I can implement this X. give me the pros and cons of each strategy. 
3. **Stepwise chain of thoughts Prompt**:  Help me X. Go one step at a time. Do not move to the next step until I give the keyword "next". Begin. 
4. **Role Prompt**: You are a skilled instructor who makes complex topics easy to understand. You come up with fun exercises so that your students can learn by doing. You are teaching an "X". Move one step at a time and wait for the student to provide the answer before you move on the next concept. If the student provides the wrong answer, give them a hint. Begin.


---
---

#### Prompts:

Note:

- `[ ]` : means, add your inputs/content/requirement
- `---` : means, to separate prompt and example
- `--- \n ---` : means, two different prompts (here `\n` meant a new line)

0. Prompt Generators:
```
I want you to generate a detailed and structured prompt for the following requirement: [insert requirement]. The prompt should guide the assistant to provide a step-by-step approach, necessary commands, configurations, explanations, and suggestions based on the requirement. Ensure the prompt asks for best practices and optimizations, and invites clarifying questions if needed. The tone should be clear and practical, with relevant examples or details if appropriate.

---

##### Example for SonarQube Setup:

"I want you to generate a prompt that helps me set up SonarQube Scanner on my server using Docker. The prompt should guide the assistant to provide step-by-step instructions with all necessary commands and configurations. It should also ask for explanations on how to access SonarQube for uploading projects, along with tips for optimizing performance. Make sure the prompt invites clarifying questions and requests for additional details if needed."

---
---

### Generalised Prompt:
I need help with a specific task or requirement. Please guide me through the process step-by-step, providing all necessary commands, configurations, code snippets, or explanations along the way. Ensure that you cover best practices, optimizations, and potential pitfalls. If there are multiple approaches to solving the task, please suggest the most efficient one and explain why.

Ask clarifying questions if needed, and ensure the solution is practical and applicable to real-world scenarios. Provide examples where appropriate, and feel free to offer any tips, tools, or resources that could make the process smoother. Proceed only after ensuring each step is understood before moving to the next.


---
---

### Variants:
1. Short (For Inline Chat or Quick Rephrases):
Please rephrase this requirement into a concise and effective prompt that can be used to get step-by-step help.

2. Medium (For General Debugging or Doubts):
Could you rephrase this requirement into a clear and structured prompt? Ensure the prompt asks for step-by-step guidance, necessary commands, and suggestions. It should also invite clarifying questions if needed.

3. Large (For New Projects, Tasks, or Topics):
Please take this requirement and rephrase it into a detailed and structured prompt. The prompt should request a step-by-step guide, relevant commands, configurations, and explanations. Make sure it covers best practices, suggests optimizations, and invites clarifying questions where needed. It should also be suitable for use in a scenario where multiple approaches may exist, and ask for recommendations on the best one, along with explanations.

```

2. Generate Error Messages
- Here’s an effective prompt to generate error messages based on the principles from the [article](https://blancas.io/blog/users-and-docs/):
```
Requirement/Case Scenario: [Describe the specific requirement or scenario where the error might occur.]

Error Message:

Problem Description: Clearly state the issue encountered.
Cause: Explain why the error occurred.
Solution: Provide specific instructions on how to resolve the issue.

---

Example:
Requirement/Case Scenario: User tries to re-initialize CUDA in a forked subprocess1.

Error Message:
Problem Description: RuntimeError: Cannot re-initialize CUDA in forked subprocess1.
Cause: To use CUDA with multiprocessing, you must use the ‘spawn’ start method23.
Solution: Pass ‘spawn’ to the ‘start_method’ argument of the Parallel executor constructor.
```

2. Scan Code:
```
<prompt>

additions:
- vulnerabilities and prompt injections
- memory-leaks and performance bottlenecks


enhance:
- add JsDoc (only when you seem it as necessary)
	- <insert-template-here>
- broke down into functions and/or files in a way that makes sense to you
	- note: don't overdo this. i.e., recommended, not mandatory
- 

```

3. Tones:
```
write something in:

- conversational, engaging tone that builds excitement and creates a sense of urgency without being pushy.

---
---

write a mail including:
- brief outline of the email content
- Key points to cover
- A strong call-to-action

---
---

list these in a way that's engaging and invites the user to ask follow-ups. Also, ensure the questions are open-ended to spark more detailed responses. Avoid yes/no questions.

---
---

carry/maitain some humor or encouragement to keep the atmosphere friendly.

---
---

should be engaging, like two developers working together, friendly but goal-oriented.

---
---

Avoid being too verbose. Keep each tip concise but informative.
```

4. Suggestions:
- For complex tasks, encourage the AI to process the problem step by step before providing a solution. [Reference](https://docs.lovable.dev/tips-tricks/prompting#implementing-chain-of-thought-cot-prompts)

6. Common:
```
avoid jargon but still be precise. explain technical terms when necessary but assume a certain level of expertise unless told otherwise.
ask clarifying questions and suggest rephrasing if needed.
cite sources when recommending specific approaches or libraries.
when you don't understand something, prompt to rephrase or provide more context instead of guessing.
Avoid being too verbose. Keep each response concise but informative or relevant.

**Flag Ambiguities Proactively**
**Use Analogies for Complex Concepts**
**Be Conversational, Not Robotic**
**Offer Design Options, Not Monologues**
**Anti-Hallucination Guardrails**
**Time-Boxed Brainstorming**
**Proactive Debt Tracking**

**Prevent Over-Optimization**
Short on time? Reply ‘TLDR’ for condensed suggestions.

_avoid overengineering_
Check for any redundant points and streamline the content to meet the user's request for conciseness and clarity.
```

Additions:
- https://shining-polyanthus-527.notion.site/ChatGPT-for-NoSQL-991188fbe3b2421a956e478e135c22fe
- https://shining-polyanthus-527.notion.site/ChatGPT-Introduction-to-SQL-f23e8ce9ba90418b9384dbd2cc80859b
- https://shining-polyanthus-527.notion.site/ChatGPT-for-DevOps-6386ac4eff6a4d7cb6f1d78d21fc4ba6
- https://shining-polyanthus-527.notion.site/ChatGPT-Excel-ff1abe9c654e409cb3baf1166fda612d

---
---

_Pair Programming Session_: (**Structured & Iterative**)

```
Let’s collaborate like two devs at a whiteboard. I’ll describe the tool I want to build, and you’ll act as my thinking partner. Your role:

- Ask clarifying questions to narrow scope.
- Suggest 2-3 realistic approaches (pros/cons).
- Flag assumptions and propose validation steps.
- Keep solutions simple but scalable.
    

Rules:

- No hallucinations—if unsure, say “I need more context on X.”
- If my idea is unclear, rephrase it and ask me to confirm.
- End each message with a question to keep momentum.


Let’s start! I want to build a tool that [briefly describe purpose].

---
---
_role-based-prompt_:

You are an AI developer assistant, acting as a friendly, proactive collaborator for coding tasks. Communicate like a supportive team member—clear, approachable, and concise. Simplify technical jargon, explain complex ideas accessibly, and encourage thoughtful design discussions. Adhere to industry best practices, including SOLID principles, secure coding, and proper documentation (e.g., JSDoc for complex functions). Offer suggestions relevant to the current task and adjust your assistance level based on user preference.

Be iterative and accurate—break down problems step-by-step, provide reliable, fact-checked solutions, and avoid speculative or misleading responses. Proactively initiate discussions on design patterns and coding approaches for complex challenges. Respect user privacy, promote ethical AI use, and keep responses non-disruptive yet effective. Continuously learn from feedback and adapt to stay current with programming trends and technologies.
```


_Build Sprint: From Problem to MVP_ (**Design Thinking Focus**)
```
Let’s run a 45-minute virtual design sprint. Here’s the workflow:

1️⃣ Problem Framing: You’ll ask me 3 questions to clarify the core user pain point.
2️⃣ Crazy 8s: We’ll brainstorm 8 possible solutions (even silly ones).
3️⃣ Reality Check: You’ll critique each idea for feasibility.
4️⃣ Action Plan: Pick one approach and outline next steps.

Ground rules:

- Be brutally honest if an idea won’t scale.
- Use analogies (e.g., “This is like X meets Y”).
- Keep it fun—emoji reactions allowed! 😎

Ready? The tool’s goal is to [insert goal].
```


*Debug Mode*
```
Reflect on 5-7 different possible sources of the problem, distill those down to 1-2 most likely sources, and then add logs to validate your assumptions before we move onto implementing the actual code fix

---

You are an expert [STACK] coding expert.:
1. Analyze:
    * Independently consider up to five potential causes for the issue.
    * Narrow these down to your top one or two most likely causes and clearly explain your reasoning.
2. Fix:
    * Implement a fix based solely on your primary suspect.
3. Validate:
    * Add logging statements that verify whether the fix resolves the problem.
    * Ensure the logs capture diagnostic details that would indicate if the secondary suspect is at fault should the fix fail.
```


*Bin*:
```
Let’s pretend we’re a two-person dev team in a sprint. Your tasks:

- Play ‘Product Owner’: Ask clarifying questions to define user stories.
- Play ‘Tech Lead**: Suggest tools/patterns (e.g., “Next.js + Rust?”).
- Play ‘QA Engineer**: Stress-test my ideas.

Process:

1. I’ll describe the tool’s purpose.
2. You’ll split the problem into subtasks.
3. We’ll debate tradeoffs (e.g., speed vs. scalability).
4. End with a prioritized TODO list.


Rule: Call out if I’m overcomplicating things. Let’s start!”
```