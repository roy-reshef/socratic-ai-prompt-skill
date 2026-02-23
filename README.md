# socratic-ai-prompt-skill
Socratic prompting is a strategy that shifts AI from a "vending machine" for answers to a "thinking partner". Instead of providing a direct answer, the AI is instructed to ask questions, challenge assumptions, or lead you to a conclusion through dialogue.
It follows the [socratic method](https://en.wikipedia.org/wiki/Socratic_method) principles.

## Core Principles
- **Interrogation Before Execution**: Force the AI to ask clarifying questions about your goal before it attempts to solve it.
- **Assumption Surfacing**: The AI identifies hidden beliefs or unstated constraints in your request.
- **Iterative Refinement**: You and the AI engage in a back-and-forth "dance" to narrow down the best possible solution.
- **Role Reversal**: You can act as the student while the AI acts as a Socratic Tutor that guides you to the answer rather than giving it to you.

## How To Use It
This skill intercepts a standard request, performs domain research (if necessary), transforms the request into a rigorous Socratic dialogue framework, and requires your sign-off before execution. <br>
### Example:
Once the skill is added to your Agent configuration:

1. Trigger it:
```
"Use the Socratic Architect to help me design a scalable microservices architecture."
```
2. Observe Research:
Agent will likely run a search command like: `google_search("common pitfalls in microservices scaling").`
3. Review the Draft:
Agent will present a prompt: `"Act as a Senior Architect. Challenge my choice of database consistency models. Ask me to justify why a monolith wouldn't suffice..."`
4. prompt refinement loop:
  - `added constriant - we use posgresqlDB`
  - `I have refined the Socratic inquiry. Should I execute this to begin our dialogue or would you like to further adjust the technical focus?`
6. Approve & Execute: `"Execute!"` <br>
Agent immediately switches modes: `"Understood. Before we discuss scaling, what specific failure domains are you trying to isolate by splitting your services?"`

## Why This Works
- **Context Awareness**: The search step ensures the AI isn't asking generic questions but knows the "hard parts" of the specific domain.
- **Approval Gate**: Prevents the frustration of the AI entering "question mode" if it misunderstood the angle you wanted to explore.
- **Persona Injection**: It effectively overwrites the original intent (getting an answer) with the new intent (finding the answer yourself).

## ✅ Use it when:
- **Architecting Systems**: When you’re choosing a tech stack or database schema and want to ensure you aren't ignoring a critical trade-off.
- **Debugging Logic, not Syntax**: When your code runs, but your approach feels "smelly" or overly complex.
- **Learning New Concepts**: When you want to truly master a library or language rather than just copy-pasting a snippet.
- **Strategic Planning**: When drafting a business model, a product roadmap, or a high-stakes email where "tone" and "perception" matter.
- **Creative Breakthroughs**: When you feel stuck in a "generic" loop and need a "sparring partner" to push you toward an original angle.

## ❌ Skip it when:
- **Transactional Tasks**: "Write a regex for email validation" or "Convert this JSON to CSV." (Just get the answer and move on).
- **Syntax Queries**: "What is the boilerplate for a React functional component?"
- **Quick Lookups**: "What is the MDN documentation for Array.reduce?"
- **Time-Sensitive Fixes**: If production is down, you don't need a Socratic dialogue; you need a solution.

## The "Rule of Thumb"
If you find yourself asking "How should I..." or "What is the best way to...", it’s a Socratic candidate. If you are asking "What is..." or "Write a...", stick to the standard prompt.
