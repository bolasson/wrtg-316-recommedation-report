# 1 Letter of Transmittal

Bryce Lasson<br/>
Software Engineer<br/>
436 Stadium Ave BSMT<br/>
Provo, UT 84604

March 14, 2026

Dr. David Wood<br/>
Team Leader, Ernst & Young Academic Resource Center (EYARC) Professor<br/>
EYARC Lab at Brigham Young University (BYU)<br/>
332 Campus Dr<br/>
Provo, UT, 84604

Dear Dr. David Wood,

I am pleased to submit my recommendation report, ***Stabilizing Speed: A Software Design Framework for AI-Assisted Development on the EYARC Experience Team***, for your review.

Because you choose whether our team invests time in a design framework, I wrote this document to assist you in development planning for the next couple of months. My report focuses on the speed of new feature delivery, reducing the amount of time spend reviewing duplicated code, and our need for solutions that students can learn quickly without slowing the team down. The recommendation is less about our past mishaps (though they will be referenced), and more about how to integrate AI without reducing our delivery speed each semester. The cause of the aforementioned speed loss is supported by research on technical debt and AI-assisted development, which suggests that “quick wins” can become expensive when systems grow without shared structure, especially when small changes can be unpredictable across a codebase (Sculley et al., 2015; Tartaglia, 2025). My report recommends adopting a lightweight, student-friendly framework that combines:

* **A small set of design rules to reduce poor coupling**—which tends to increase maintenance effort as the application evolves (Yanakiev et al., 2025). 
* **A prompt-template library (based on few-shot prompting) so AI output matches our preferred structures**, reducing inconsistency and time lost to refactoring (Esposito et al., 2026). 
* **A “human-first” review protocol to guard against automation bias**, keeping students accountable for understanding and testing changes before merging (Romeo & Conti, 2026). 

I am optimistic that this approach aligns with your three priorities for our team.

1. **Ease of learning for students.** Evidence from programming education suggests that AI can support cleaner, less complex code when students are guided by conventions and standards (Haindl & Weinberger, 2024). 
2. **Reasonable creation time for the guide.** My report proposes packaging guidance in an “actionable skills” format (short, structured, reusable) similar to how software development teams publish best-practice modules for agents, which is helpful for fast onboarding and consistent application (Pierzchała, 2026). 
3. **Development time savings for new features.** Industry and academic sources share a consistent theme: AI tends to deliver strong ROI when teams reduce rework with context, patterns, and disciplined review (Sergeyuk et al., 2024; Tartaglia, 2025). When these patterns aren't used, like we do, the review and debugging overhead can decrease the speed gained when using AI. (Sergeyuk et al., 2024; Tartaglia, 2025). 

As a student developer, my perspective is very focused on how this could be implemented and my own design biases. As such, I’ve tried to be careful about overclaiming. Where possible, I've built my proposed framework using external ideas and studies, such as how to refactor using design principles in large systems (Yanakiev et al., 2025), how to create maintainable code using design patterns and multi-agent workflows (Wang et al., 2025), and human in the loop practices that reduce overreliance on AI outputs (Esposito et al., 2026; Romeo & Conti, 2026).

Thank you for taking the time to consider this recommendation. If you decide the approach is worthwhile, my report closes with a recommend starting plan, which you can adjust as you and our project manager see fit. The starting plan includes a short design-pattern guide, a small prompt library filled with our best code examples, and a review routine that keeps humans responsible for all AI generated code. I hope you find this useful as you strive to improve our teams speed and results.

Sincerely,<br/>
<img src="./01_letter_of_transmittal/Signature.png" alt="Bryce Lasson's Signature" width="250" height="50"><br/>
Bryce Lasson

# 2 Title Page
### Stabilizing Speed: A Software Design Framework for AI-Assisted Development on the EYARC Experience Team

Bryce Lasson

Department of Computer Science, Brigham Young University

WRTG 316: Technical Communication

Dr. Nicole Clawson

March 14, 2026

# 3 Executive Summary

Our team is moving fast with AI-assisted development. AI helps us write code quickly, but we do not have a shared system for how that code should be structured, reviewed, or matched to the rest of our app. Because of that, time saved early can be lost later through debugging, refactoring, and dependency problems. Research supports that risk. Tartaglia reports that experienced developers on familiar codebases took 19% longer when AI suggestions required extra review, validation, and debugging. Sculley et al. also warn that quick wins in complex systems often create long-term maintenance costs when structure is weak. Our team has seen these quick wins, time losses, and weak structure, evident in our prior database refactors, but we have another factor contributing to our situation.

Everyone on our team is currently a student, so we also deal with the challenges that come with student turnover and varying experience levels. Research on student programmers shows that AI can help students produce code with fewer errors and lower complexity, but the final work still reflects both AI output and student revision (Haindl & Weinberger, 2024). Part of this problem is that our team does not always fully understand the code AI generates. Our weak structure may also be due to a lack of thorough review. Research on automation bias shows that people can favor automated recommendations too quickly, especially when the workflow does not require active human judgment before seeing AI output (Romeo & Conti, 2026). Put together, these student risks suggest that our problem is not AI alone, but the lack of a shared process for how we use it. The next step is to decide how our team should move forward.

I considered three options. The first is to continue using AI without shared constraints. The second option is to create an integrated software design framework that uses software design patterns, prompt templates, and human-first review. The third option is to move toward a custom multi-agent lifecycle model. I'd recommend a phased approach built from two of the three options. I recommend adopting a design framework now that uses clear design rules, a small prompt-template library built from strong internal examples, and a human-first review process. Then, as our needs grow, we can build toward a multi-agent model. I believe this approach will give us the best chance of keeping the benefits of AI without letting our codebase get harder to maintain each semester.

# 4 Introduction

The EYARC Experience Team uses AI because it helps us move faster. But that speed has come with a cost. In our current workflow, AI-generated code has introduced bugs, weak structure, and technical debt that requires constant upkeep. We have seen this in our own work when quick solutions later turned into refactors, dependency issues, and extra review time. What looks fast at the start does not always stay fast once that code has to be maintained, extended, or understood by a new group of students.

This issue matters even more because our team is built around student developers. Students graduate, move on, and join at different skill levels, so the codebase has to survive constant turnover. That makes consistency especially important. If our structure is weak, new students have a harder time understanding old code, and small problems are more likely to grow into bigger ones. AI can help us work faster, but on a student team like ours, speed without shared rules can make the problem worse instead of better.

Because of that, I am proposing a framework built around what I call "Stabilizing Speed". By that, I mean creating a framework with clear rules that help students and AI work together to improve both production speed and code quality. My report argues that our team needs a framework so we can keep moving quickly without creating more long-term maintenance problems.

This report first explains the problem by looking at technical debt, student turnover and skill gaps, system fragility, and automation bias. It then examines three options: continuing with unconstrained AI assistance, adopting an integrated software design framework, or moving toward a custom multi-agent lifecycle model. It closes by recommending a phased plan that starts with the design framework and treats multi-agent verification as a future direction.

# 5 Problem Description
## 5.1 Technical Debt and Skill Gaps

Right now, the EYARC Experience Team at BYU is in a tough spot with how we build software. Even though using AI has helped us write code faster, it has also caused a lot of bugs and long-term problems because we don't have a set plan for how to use it. This section looks at why this is happening, focusing on how our student team setup, the use of AI tools, and a lack of clear rules all work together to create these issues.

One big reason we are struggling is because our team is mostly students, which comes with two main problems. The first is a high employee turnover rate. This turnover rate creates a "gap" in what we know about our work and platform since the people who wrote the code aren't around. The second is that many of us are still learning the basics of software design while trying to maintain our team's main web app. Because we are still gaining experience, it is very hard to keep the code consistent when the team changes so often and we don't have a standard set of rules to follow. These human factors create a fragile foundation that makes technical problems even worse.

This lack of experience among our team members often leads us to rely heavily on AI tools like Antigravity and Codex, but using these tools without a plan can be highly time consuming in the long run. Right now, a lot of our development time is spent fixing mistakes or rewriting code from old features instead of building new things. This suggests that without a clear structure, the time we "save" with AI at the start is just being lost later when the code breaks. If we don't create a real plan for how we use AI together as a team, we could keep spending more time fixing bugs than actually finishing projects.

## 5.2 Technical Root Causes

The way we build our main web app might be causing bugs as it gets bigger. Without a set of rules for the AI to follow, the results often focus on just getting the job done right now instead of thinking about how the code will look in a year. Research shows that without design patterns to guide them, developers and AI often build "fast and flimsy" solutions that are hard to change later (Supekar & Khande, 2024). On our team, this means we get code that works once, but then it breaks the moment we try to add a new feature because it wasn't built with a long-term plan in mind. A prime example of this was the `course_assignment_settings_form` that we developed recently. Multiple students were working on it using AI, and because we didn't have a set plan, it ended up with an inconsistent structure and caused a lot of errors. Now, our team is spending time refactoring it rather than working on new assignments.

Another issue is how AI code can accidentally mess up other parts of our system without us realizing it. This is often called the "Changing Anything Changes Everything" principle—a concept originally describing machine learning systems that can also apply to our software architecture (Sculley et al., 2015). This can make the whole app feel fragile because one small change might cause a bug in a completely different spot. I have seen this happen in our own app: it is currently causing issues between our database and our Auditing Inventory Simulation. This demonstrates a big gap between the architecture we want and the actual code the AI writes for us. Many times, the AI creates logic that lacks basic structural integrity, such as failing to check for variable consistency or making the code difficult to follow (Sergeyuk et al., 2025). These "gaps" in the AI's logic mean that we have to be the ones to provide the structure, or the system will continue to erode as we add more features.

## 5.3 Behavioral Root Causes

Our problems aren't just technical; they are also about how we think when we use AI tools. We have fallen into some habits that make it harder to catch mistakes, such as "automation bias." This happens when we trust the AI too much just because it's a computer (Romeo & Conti, 2026). I've seen students merge code they don't fully understand because they think the AI knows more than they do. This is a big problem because it lets bugs into our main branch that could have been caught if we were paying more attention. When we stop questioning the output, we stop acting like engineers and start acting like copy-pasters.

It is also very easy to let the AI handle the hard parts of coding, but this can backfire without a plan to double-check the results. We often think we are moving faster, but spending hours debugging AI mistakes can take more time than just writing it ourselves. Research in enterprise settings shows that experienced developers can take up to 19% longer to finish tasks with AI because they have to fix so many errors (Tartaglia, 2025). For students like us who are still learning, that number is likely even higher because we don't always have the background to fix what the AI broke. We should not let the instant nature of AI fool us into thinking we are being productive without a plan to keep our code organized.

In the end, the bugs and long-term problems we are seeing at the EYARC Experience Team come from combining powerful AI tools with a student team that doesn't have a consistent set of rules to follow. I think we should stop relying on "fast and flimsy" results and start using a framework that keeps our code clean and reliable as students come and go, and as our use of AI continues to grow. These behavioral habits are just as dangerous as the technical ones, and they must be addressed together. Because both our technical structure and our team behavior contribute to this instability, any solution must address both.

# 6 Options and Potential Solutions

To help fix the issues we are having with buggy code and long-term instability, we have three main options. We can keep doing things the way we are right now, we can start using a software design framework, or we can explore a multi-agent lifecycle model.

## Option A: Unconstrained AI Assistance

Right now, everyone at the EYARC Experience Team just uses AI however they want without any specific rules. This is easy to start with because we don't have to learn any new systems, but it is causing a lot of problems as our main web app gets older.

The main issue is that while writing code is fast at first, the app becomes unstable because the AI doesn't know our overall design. This causes a knowledge gap where the code becomes much harder to manage as students graduate. Research on "technical debt" shows that when code is built without a plan, we spend more time trying to understand and fix old mistakes than we do building new features (Tartaglia, 2025). This is exactly what we are seeing on the EYARC Experience Team. I believe that if we stay on this path, our code could become so messy that our AI usage eventually stops being productive, or even more time consuming than coding on our own.

## Option B: Integrated Software Design Framework

I believe one strong option is to build a framework that requires the AI to follow certain design rules. This plan focuses on three key areas: using structural rules for the code, setting up prompt templates, and making sure humans stay in charge of the final decisions.

### Structural SOLID Principles

First, we should ensure our code follows the SOLID principles, a set of five rules that keep software from becoming harder to maintain over time (Yanakiev et al., 2025). A core part of the SOLID principles is the Dependency Inversion Principle (DIP). The DIP states that our high-level logic should stay separate from the low-level tools we use. This keeps different parts of the code from being too tangled up. To better illustrate the DIP, let us dive into an example.

Think of our code like a TV and its remote. If the remote is built to only work with one specific TV, you have to buy a new remote the moment the TV breaks. But if the remote is built to work with a TV interface, it can control any TV regardless of the brand. When our code is tangled, it's like having a remote glued to one TV. For example, if we change how we store data in our database, we might have to rewrite an entire assignment or simulation to work with it. By using an abstraction, we can change the low-level tools (the TV), without breaking the high-level logic (how to change a channel remotely). That's the Dependency Inversion Principle in practice. It would make a large difference for our team because then students know exactly where to go based on dependencies: and that’s just one of the SOLID principles.

Other teams and companies have seen great results with the SOLID approach. For example, a study on the ASML company showed that when they used these patterns, they were able to cut down bad code dependencies by 50% across thousands of files (Yanakiev et al., 2025). Peking University researchers also found that forcing AI to use design patterns made code 60% easier to maintain (Wang et al., 2025). If we use these same patterns, we can ensure our development follows high standards and make it easier for new students to join the team and understand how everything fits together. This separation directly prevents the cascading bugs we are currently experiencing.

### Prompt Templates

Next, we can improve how we talk to the AI by using specific templates for our prompts. We considered using a Retrieval-Augmented Generation (RAG) system, but that might be more work than we need right now. Instead, we can just give the AI specific examples of our best code to copy. Research shows that giving AI a few good examples (called "few-shot learning") can drastically improve its results (Nashid, 2023). This helps stop the AI from just copy-pasting random code that doesn't fit our project (Tartaglia, 2025). By using these blueprints, we can make sure the AI builds things in a way that matches what we've already written without adding extra technical overhead.

**Figure 1**<br/>
Title

<img src="./PromptTemplates.png" alt="Example implementation of a prompt template system" width="700" height="400" style="display: block; margin: 0 auto;">

_Note._ Short explanation of the image, where it was taken from, what page it was.
<p>Pg 772</p>   

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

# 7. Conclusion and Implementation Recommendation

The EYARC Experience Team has a clear opportunity to stop the cycle of bugs and long-term instability by changing how we use AI. While writing code quickly is a benefit, it is becoming clear that we cannot ignore the long-term cost of flimsy, unorganized software. By adopting a "Stabilizing Speed" framework built first on clear design rules, prompt guidance, and human-first review, the EYARC Experience Team can reduce long-term instability while preserving the speed benefits of AI. Over time, that framework could expand toward multi-agent verification as the team’s needs grow.

## The ROI Argument: Stabilizing Speed

We can justify this change by looking at the return on our time. If we don't start using these design rules, we will reach a point where fixing AI mistakes costs more than the time the AI saved us in the first place (Tartaglia, 2025). This tipping point could significantly reduce our productivity. However, research shows that these patterns can make code 60% easier to manage (Wang et al., 2025). By significantly reducing our bug-fixing time, we can get more work done without needing more people on the team, turning the "illusion of speed" into real productivity.

## Action Plan: Phased Implementation

To get started, I recommend three immediate steps to bridge the gap between our current work and this new framework:

1.  **Create a Design Pattern Guide**: We need to formally write down the coding rules we want everyone to follow, such as the Dependency Inversion Principle. This includes selecting a standard UI architecture (MVC, MVP, or MVVM) and prioritizing the implementation of core design patterns like Observer, Factory, and Template Method. This will be the core of our design framework for both students and the AI.
2.  **Develop a Prompt Library**: We should build a library of proven prompt blueprints using few-shot learning and multi-agent verification (Wang et al., 2025). This will prevent us from repeating the same basic AI mistakes and ensure our results match the team's high standards from the start.
3.  **Use "Human-First" Reviews**: We must change our workflow so that we write our own plans and tests before using AI tools (Romeo & Conti, 2026). This keeps our skills sharp and ensures we stay in control of the code instead of just letting AI decide how we build our apps. This protocol will help us catch bugs much earlier in the process.

These rules are not meant to slow us down. Instead, they provide the foundation our team needs to build better software and be more productive.
