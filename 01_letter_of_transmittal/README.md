March 14, 2026

Bryce Lasson
Software Developer
436 Stadium Ave BSMT
Provo, UT 84604

Ernst & Young Academic Resource Center (EYARC)
Dr. David Wood
N. Eldon Tanner Building (TNRB), Brigham Young University
332 Campus Dr
Provo, UT 84604

Dear Dr. David Wood,

I am pleased to submit my recommendation report, ***Stabilizing Speed: A Software Design Framework for AI-Assisted Development on the EYARC Experience Team***, for your review.

Because you choose whether our team invests time in a design framework, I wrote this document to assist you in development planning for the next couple of months. My report focuses on the speed of new feature delivery, reducing the amount of time spend reviewing duplicated code, and our need for solutions that students can learn quickly without slowing the team down. The recommendation is less about our past mishaps (though they will be referenced), and more about how to integrate AI without reducing our delivery speed each semester. The cause of the aforementioned speed loss is supported by research on technical debt and AI-assisted development, which suggests that “quick wins” can become expensive when systems grow without shared structure, especially when small changes can be unpredictable across a codebase (Sculley et al., 2015; Tartaglia, 2025). My report recommends adopting a lightweight, student-friendly framework that combines:

* **A small set of design rules to reduce poor coupling**—which tends to increase maintenance effort as the application evolves (Yanakiev et al., 2025). 
* **A prompt-template library (based on few-shot prompting) so AI output matches our preferred structures**, reducing inconsistency and time lost to refactoring (Esposito et al., 2026). 
* **A “human-first” review protocol to guard against automation bias**, keeping students accountable for understanding and testing changes before merging (Romeo & Conti, 2026). 

I am optimistic that this approach aligns with your three priorities for are team.

1. **Ease of learning for students.** Evidence from programming education suggests that AI can support cleaner, less complex code when students are guided by conventions and standards (Haindl & Weinberger, 2024). 
2. **Reasonable creation time for the guide.** My report proposes packaging guidance in an “actionable skills” format (short, structured, reusable) similar to how software development teams publish best-practice modules for agents, which is helpful for fast onboarding and consistent application (Pierzchała, 2026). 
3. **Development time savings for new features.** Industry and academic sources share a consistent theme: AI tends to deliver strong ROI when teams reduce rework with context, patterns, and disciplined review (Sergeyuk et al., 2024; Tartaglia, 2025). When these patterns aren't used, like we do, the review and debugging overhead can decrease the speed gained when using AI. (Sergeyuk et al., 2024; Tartaglia, 2025). 

As a student developer, my perspective is very focused on how this could be implemented and my own design biases. As such, I’ve tried to be careful about overclaiming. Where possible, I've built my proposed framework using external ideas and studies, such as how to refactor using design principles in large systems (Yanakiev et al., 2025), how to create maintainable code using design patterns and multi-agent workflows (Wang et al., 2025), and human in the loop practices that reduce overreliance on AI outputs (Esposito et al., 2026; Romeo & Conti, 2026).

Thank you for taking the time to consider this recommendation. If you decide the approach is worthwhile, my report closes with a recommend starting plan, which you can adjust as you and our project manager see fit. The starting plan includes a short design-pattern guide, a small prompt library filled with our best code examples, and a review routine that keeps humans responsible for all AI generated code. I hope you find this useful as you strive to improve our teams speed and results.

Sincerely,
![Bryce Lasson's Signature](./Signature.png)
Bryce Lasson