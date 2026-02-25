# 6.1 Options and Potential Solutions

To help fix the issues we are having with buggy code and long-term instability, we have two main choices. We can either keep doing things the way we are right now with "fast and flimsy" AI, or we can start using a real software design plan to keep our main web app organized. To mitigate the risks of unconstrained AI, a more structured approach is required.

## Option A: Unconstrained AI Assistance

Right now, everyone at the EYARC Experience Team just uses AI however they want without any specific rules. This is easy to start with because we don't have to learn any new systems, but it is causing a lot of problems as our main web app gets older.

The main issue is that while writing code is fast at first, the app becomes unstable because the AI doesn't know our overall design. This causes a knowledge gap where the code becomes much harder to manage as students graduate. Research on "technical debt" shows that when code is built without a plan, we spend more time trying to understand and fix old mistakes than we do building new features (Tartaglia, 2025). This is exactly what we are seeing on the EYARC Experience Team. I believe that if we stay on this path, our code could become so messy that our AI usage eventually stops being productive, or even more time consuming than coding on our own.

## Option B: Integrated Software Design Framework

I believe one strong option is to build a framework that requires the AI to follow certain design rules. This plan focuses on three key areas: using structural rules for the code, setting up prompt templates, and making sure humans stay in charge of the final decisions.

### SOLID Principles

First, we should ensure our code follows the SOLID principles, a set of five rules that keep software from becoming harder to maintain over time (Yanakiev et al., 2025). A core part of this is the Dependency Inversion Principle. This basically means that our main logic should stay separate from the low-level tools we use. This keeps different parts of the code from being too tangled up. Let me give you an example.

Think of our code like a universal remote. If the remote is built to only work with one specific TV, you have to buy a new remote the moment the TV breaks. But if the remote is built to work with a TV interface, it can control any TV regardless of the brand. When our code is tangled, it's like having a remote glued to one TV. If we change how we store data in our database, we might have to rewrite an entire assignment or simulation. By using an abstraction, we can change the low-level tools (the assignment or simulation) without breaking the high-level logic (the database and assignment loader). That's the Dependency Inversion Principle in practice, and it would make a large difference for our team.

Other teams and companies have seen great results with this approach. For example, a study on the ASML company showed that when they used these patterns, they were able to cut down bad code dependencies by 50% across thousands of files (Yanakiev et al., 2025). Peking University researchers also found that forcing AI to use design patterns made code 60% easier to maintain (Wang et al., 2025). If we use these same patterns, we can ensure our development follows high standards and make it easier for new students to join the team and understand how everything fits together. This separation directly prevents the cascading bugs we are currently experiencing.

### Prompt Templates

Next, we can improve how we talk to the AI by using specific templates for our prompts. We considered using a Retrieval-Augmented Generation (RAG) system, but that might be more work than we need right now. Instead, we can just give the AI specific examples of our best code to copy. Research shows that giving AI a few good examples (called "few-shot learning") can drastically improve its results (Nashid, 2023). This helps stop the AI from just copy-pasting random code that doesn't fit our project (Tartaglia, 2025). By using these blueprints, we can make sure the AI builds things in a way that matches what we've already written without adding extra technical overhead.

### Human Oversight

Lastly, we need to make sure we don't just blindly trust what the AI tells us. Experts suggest building "friction" into our workflow to make sure humans stay involved (Romeo & Conti, 2026). This means we should have a rule where we write out our own plan or tests for a feature before we even open an AI tool (Esposito et al., 2026). This forces us to actually understand the problem we are solving instead of just letting the AI guess for us. It keeps us in control and helps us become better engineers as we gain experience.

## Option C: Custom Multi-Agent Lifecycle Model

Recent advancements in multi-agent verification provide a potential path forward. For example, Peking University research shows that this "ChatDev" style of multi-agent verification can achieve much higher success rates because each agent is forced to verify and check the work of the previous one (Wang et al., 2025). This can catch the types of "hallucinations" or logical gaps that a single AI model might miss. While this is more complex to set up, it could provide a very stable foundation and help us move away from inconsistent code structures (Callstack, 2026). This would be a perfect long-term goal for the team as our projects grow.

## Summary of Options

| Feature                    | Option A: Unconstrained AI Assistance | Option B: Design Framework | Option C: Multi-Agent Model |
| :------------------------- | :-------------------------- | :------------------------- | :-------------------------- |
| **Initial Delivery Speed** | Very High                   | High                       | Moderate                    |
| **Long-term Reliability**  | Low (System breaks easily)  | High (+60% Stability)      | Very High                   |
| **Fixing Old Code**        | A large portion of our time | Much lower (Estimated)     | Extremely Low               |
| **Learning Curve**         | Very Low                    | Moderate                   | High                        |
| **Value for Money**        | Low (Wasted time)           | High (Very stable)         | Very High                   |

I believe that a combination of parts from Option B and Option C represents the best path forward. By using these design patterns to keep our code organized and review rules to keep our skills sharp, we can get the speed of AI without the constant bugs that keep slowing us down. Given the strengths and tradeoffs of each option, the next step is deciding how we should move forward.
