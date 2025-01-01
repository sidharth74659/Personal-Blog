


**Reads:**
- https://docs.github.com/en/github-models/prototyping-with-ai-models
	- https://github.com/marketplace/models
- [Anthropic Cookbook](https://github.com/anthropics/anthropic-cookbook?tab=readme-ov-file): Code and guides designed to help build. 



**Prompt Engineering:**
- [ ] https://www.uber.com/en-IN/blog/introducing-the-prompt-engineering-toolkit/?=&aid=recbxr9IRM7UNGV8S
- [ ] https://docs.lovable.dev/tips-tricks/prompting
- [ ] (video) [AI prompt engineering: A deep dive](https://www.youtube.com/watch?v=T9aRN5JkmL8)
- [ ] Sites:
	- [ ] Prompt Tools: https://webcurate.co/c/prompt

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

```

4. Suggestions:
- For complex tasks, encourage the AI to process the problem step by step before providing a solution. [Reference](https://docs.lovable.dev/tips-tricks/prompting#implementing-chain-of-thought-cot-prompts)


Additions:
- https://shining-polyanthus-527.notion.site/ChatGPT-for-NoSQL-991188fbe3b2421a956e478e135c22fe
- https://shining-polyanthus-527.notion.site/ChatGPT-Introduction-to-SQL-f23e8ce9ba90418b9384dbd2cc80859b
- https://shining-polyanthus-527.notion.site/ChatGPT-for-DevOps-6386ac4eff6a4d7cb6f1d78d21fc4ba6
- https://shining-polyanthus-527.notion.site/ChatGPT-Excel-ff1abe9c654e409cb3baf1166fda612d