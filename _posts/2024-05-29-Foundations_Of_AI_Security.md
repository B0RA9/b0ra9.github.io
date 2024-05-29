---
title: Foundations Of AI Security 1
layout: post
categories: [Notes, AI]
tags: [ai,security]     # TAG names should always be lowercase
---
  These are some notes from the `Foundations Of AI Security` course provided by [AttackIQ](https://www.attackiq.com).
  They might be modified/imporoved to make a better AI security resource.
  
*<h1><span style="color:Green"> Types Of AI </span></h1>*

**There are three kinds of artificial intelligence based on capabilities :**

<span style="color:red">1) **Artificial Narrow AI :**</span>
This is the only type of AI that is not theoretical as of the writing of this course. It is trained on a
narrow task that it does well, but cannot work outside of.
`ANI systems in healthcare diagnostics can analyze medical images, such as X-rays or MRIs, with precision that matches or exceeds human performance`

<span style="color:red">2) **General AI :**</span>
This is a theoretical concept that allows existing knowledge and skills to accomplish tasks in different contexts. Training of the underlying models by humans would not be required. General AI represents a leap from AI capable of performing specific tasks (ANI) to systems that can understand, learn, and apply knowledge in different contexts, much like a human.

<span style="color:red">**3) Super AI :**</span>
This is also a theoretical concept that if ever created would think, reason, learn make judgments, and possess the cognitive abilities of human beings.

**There are four types of artificial intelligence based on functionalities:**

**1) Reactive Machine AI:**
Systems with no memory that are designed to perform a specific task.
`A notable real-world example is the use of robotic arms by companies in their manufacturing plants`

**2) Limited Memory AI :**
Can recall past events and outcomes and monitor specific objects or situations over time.
`use these principles to create dynamic learning pathways that adjust based on the learner's performance, enhancing engagement and efficacy.`

**3) Theory of Mind AI :**
This falls under General AI and therefore is only theoretical. If this functionality were to become real it would understand the thoughts and emotions of other entities and would affect how the system interacts with the world around i

**4) Self-Aware AI :** 
This falls under Super AI and is also only theoretical. If the functionality were to be realized it would have the ability to understand its own internal conditions and traits along with human emotions and thoughts

*<h1><span style="color:Green">AI Lifecycle</span></h1>*

1) **Plan and Design**

2) **Collect and Process Data**

3) **Build and Use Model** 

4) **Verify and Validate**

5) **Deploy and Use**

6) **Operate and Monitor**

7) **The final stage** involves creating a feedback loop where the outcomes of the model's predictions (such as the success of targeted retention efforts) are used to further refine and improve the model. This can involve collecting new types of data, tweaking the model based on performance, and even revisiting the problem definition if necessary.

- The National Institute of Standards and Technology (NIST) introduced the AI Risk Management Framework (AI RMF) on January 26, 2023
- The AI RMF by NIST addresses these unique challenges by providing a structured approach to managing risks associated with the development, deployment, and operation of AI systems, emphasizing the importance of transparency, accountability, and ethical considerations in AI applications.
- AI system impact assessment approaches can help AI actors understand potential impacts or harms within specific contexts. An AI Impact Assessment (AIIA) is a systematic process designed to evaluate the potential effects and risks associated with the deployment of artificial intelligence systems within specific contexts. This assessment is crucial for understanding the broader implications of AI technologies, including ethical, social, legal, and economic impacts. The goal of an AIIA is to identify potential negative outcomes before they occur, enabling organizations to implement mitigation strategies proactively.

*<h1><span style="color:Green">Risk at Different Stages of the AI Lifecycle</span></h1>*

- Plan and Design: During this initial phase, the focus is on identifying potential design flaws or biases in the data that could lead to unfair outcomes or inaccuracies
- Verify and Validate Stage: At this point, the emphasis shifts to assessing the AI system's performance under various conditions to ensure its reliability and safety. Testing might reveal that the system performs well under controlled conditions but fails to generalize to real-world scenarios, posing a risk of unreliable outputs when deployed
- Deploy and Use Stage: Once the AI system is deployed, the risk measurement involves monitoring its operation in live environments to identify any emergent risks, such as unexpected user interactions or manipulation by malicious actors.
- Operate and Monitor Stage: This ongoing phase involves tracking the AI system's performance over time, adapting to new data, and addressing any issues that arise from its interaction with the environment or users.

**AI Actors :**

- Developers and Engineers primarily focus on technical risks, such as software bugs, data integrity issues, and system performance, striving to build reliable and efficient AI systems.
- Business Users are concerned with risks related to the AI system's impact on operational efficiency, return on investment, and how well the system aligns with business objectives.
- Regulators and Policymakers emphasize compliance risks, ensuring that AI systems adhere to legal and regulatory standards, particularly regarding privacy, security, and fairness.
- The Affected Communities and end-users are most concerned with social and ethical risks, such as privacy infringement, discrimination, and transparency in how the AI system affects their lives and decisions made about them.

>## Lab Vs Real World Environment :

**Lab:** 

<span style="color:red">**Advantages:**</span>

- Controlled Environment: Allows for the isolation of variables to understand the AI system's behavior in specific situations.
- Repeatability: Experiments can be repeated under the same conditions to validate findings.
- Safety: Testing in a simulated environment poses no risk to the public.

<span style="color:red">**Limitations:**</span>

- Simplification of Scenarios: May not capture the full complexity of real-world environments.
- Lack of Real-World Interactions: Does not account for unpredictable human behavior or unexpected environmental variables

**Real World :** 

<span style="color:red">**Challenges:**</span>

- Unpredictability: Real-world environments introduce variables that are difficult to predict or simulate accurately in a lab.
- Complexity: The AI system must navigate complex scenarios that involve nuanced human behaviors and interactions.
- Safety and Ethical Concerns: There's a higher risk of accidents, raising ethical questions about testing AI systems in public spaces.

>### **Key Differences:**
>- Scope of Risk Measurement: Real-world testing must account for a broader range of risks,including those related to safety, ethics, and interaction with humans and other systems in an uncontrolled environment.
>- Data Variability: Real-world environments provide a richer, more diverse dataset, which is crucial for training AI systems but also introduces more variables and uncertainty into risk assessment.
>- Stakeholder Impact: The potential impact on and feedback from actual users, pedestrians,and other stakeholders in real-world settings are critical components of risk assessment that are absent in laboratory settings.

**Human Baseline :**

AI systems can analyze large datasets to make investment recommendations much faster than human financial analysts. However, humans bring to the table an understanding of market psychology, regulatory changes, and economic indicators that might not be fully quantifiable. Baseline metrics for comparison would need to include not only the accuracy and speed of analysis but also the ability to integrate qualitative insights and adapt to market changes

**Risk Tolerance :**

The AI Risk Management Framework (AI RMF) helps in prioritizing risks but does not define how much risk an organization or AI actor is willing to accept—this concept is known as risk tolerance. Risk tolerance is essentially how much risk an organization is prepared to handle to meet its goals, and it can vary based on legal or regulatory requirements. What constitutes an acceptable level of risk can differ greatly depending on the context, specific applications, and use cases.

**Challenges to Risk Prioritization :**

**Residual risk :** or the risk remaining after mitigation efforts, has direct consequences for users and communities. Documenting these risks helps system providers understand the deployment implications and informs users about potential negative impacts.

The AI Risk Management Framework (RMF) advises prioritizing the highest risks within specific contexts. AI systems posing unacceptable risks should have their development or deployment paused until these risks are under control. Systems with lower risks may be deprioritized

**Predictive policing :**

- Unrealistic Expectations: Law enforcement agencies might aim to completely eliminate crime through predictive policing. However, expecting the AI system to predict every incident accurately is unrealistic due to the dynamic nature of human behavior and the complexity of social factors influencing crime
- Strategic Resource Allocation: Recognizing that not all risks are the same, the agency decides to allocate resources more thoughtfully
- Prioritization Based on Risk Level: The AI system might identify certain neighborhoods as high risk, prompting immediate attention. However, the agency evaluates the potential impact of acting on these predictions, considering the risk of social unrest or community distrust
- Residual Risk Communication: The police department documents and communicates the limitations and potential biases of the predictive policing system, informing both officers and the community about the residual risks.

**Organizational Integration & Management of Risk :**

- Cybersecurity Risks: Implementing strong data encryption and regular security audits to protect against hacking and data breaches.
- Privacy Risks: Ensuring the chatbot collects and processes customer data in compliance with privacy laws, such as GDPR or CCPA, including obtaining consent where necessary.
- AI-specific Risks: Regularly reviewing the chatbot's responses for accuracy and bias, and updating its algorithms to prevent discriminatory or inaccurate responses.

**Trustworthiness:**

Trustworthy AI systems are characterized by their validity, reliability, safety, security, resilience, accountability, transparency, explainability, interpretability, privacy enhancement, and fairness, with effective management of harmful biases. These characteristics are deeply connected to the social and organizational contexts in which AI systems are deployed, the data they use, the selection of models and algorithms, and how humans oversee and interact with these systems.

Trustworthiness in artificial intelligence (AI) is a multifaceted concept that requires a holistic approach to ensure AI technologies are used ethically and responsibly. Each component of trustworthiness plays a crucial role in the development and deployment of AI systems:

**Validation** refers to the process of confirming that an AI system accurately meets the specified requirements. For example, a loan approval AI must be validated to ensure it effectively assesses borrower risk based on the defined criteria.

**Reliability** is the consistency of an AI system in performing its intended functions under varying conditions. A reliable voice recognition system, for instance, consistently interprets commands accurately, regardless of the user's accent or background noise.

**Accuracy** pertains to the precision with which an AI system makes predictions or decisions. A weather prediction AI, for example, is deemed accurate if it forecasts weather events with a high degree of correctness, based on well-defined test sets that mirror expected real-world conditions.

**Safety** in AI involves designing systems that protect users and the environment from harm. An autonomous vehicle, for instance, must have safety mechanisms to detect and respond to unexpected obstacles, thereby safeguarding human life and property.

**Security** relates to the protection of AI systems against unauthorized access, cyber-attacks, or data breaches. A financial fraud detection system's resilience in the face of cyber-attacks exemplifies the importance of security in maintaining the integrity of AI applications.

**Accountability** is the assignment of responsibility for the decisions and outcomes of an AI system. For instance, a social media platform using AI for content filtering should have clear policies detailing the decision-making processes and responsibilities.

**Transparency** involves openly sharing information about how an AI system operates, including its decision-making processes, data sources, and criteria. A job application screening AI that transparently ranks candidates fosters trust and understanding among users.

**Explainability** refers to the ability of an AI system to provide understandable reasons for its decisions or predictions. A credit scoring AI that explains its scoring process helps users grasp the rationale behind its decisions.

**Interpretability** is closely related to explainability and refers to the degree to which users can comprehend and trust the outputs of an AI system. A healthcare AI system that provides interpretable treatment recommendations ensures that clinicians can align the outputs with the intended functional purposes.

**Privacy enhancement** in AI involves implementing techniques to protect sensitive data and user privacy. An AI-powered marketing tool that uses data minimization techniques exemplifies a commitment to safeguarding user privacy while delivering targeted content.

**Fairness** ensures that AI systems do not perpetuate or amplify biases and that their decision making processes are equitable. An AI hiring tool designed to mitigate bias and ensure fairness is crucial in preventing discrimination against any demographic group.

>*<h1><span style="color:Green">AI RMF Core</span></h1>*

The Core framework consists of four main functions: govern, map, measure, and manage. These functions are further divided into categories and sub-categories, which detail specific actions and outcomes to be achieved.

<h3><span style="color:red"> Govern</span></h3>

The "Govern" function plays a crucial role in fostering a culture of risk management within organizations that are involved in any stage of AI systems' lifecycle, including design, development, deployment, evaluation, or acquisition. It sets the foundation by establishing detailed processes, documentation, and organizational structures aimed at proactively anticipating, identifying, and managing potential risks that AI systems might pose, not just to users but also to wider society.

This includes setting up clear procedures to achieve desired outcomes, assessing potential impacts, and ensuring that AI risk management efforts are in harmony with the organization's core principles, policies, and strategic objectives.

<h3><span style="color:red">Map</span></h3>

The Map function plays a crucial role in establishing the context for framing risks associated with AI systems. It acknowledges the complex interdependencies among various activities and relevant AI actors, which often complicates the ability to accurately predict the impacts of AI systems. By executing the Map function, organizations gather vital information that not only aids in preventing negative risks but also guides critical decisions related to model management and evaluates the suitability or necessity of an AI solution.

<h3><span style="color:red">Measure</span></h3>

The Measure function utilizes a variety of tools and methods, both quantitative and qualitative, to thoroughly analyze, evaluate, benchmark, and keep track of the risks associated with AI systems and their broader impacts. It's crucial for AI systems to undergo rigorous testing not only before they are deployed but also consistently during their operation. This process involves monitoring metrics that reflect the trustworthiness of the AI, its social impact, and how humans interact with the AI system

<h3><span style="color:red">Manage</span></h3>

The Manage function is about consistently directing resources towards managing the risks that have been pinpointed and evaluated, in line with the rules laid out by the Govern function. It leverages expert advice and input from key AI participants, identified during the Govern phase and further explored in the MAP phase, aiming to reduce system failures and negative outcomes. Starting from the Govern phase and carried through Map and Measure, meticulous documentation practices play a key role in improving risk management by making processes more transparent and accountable.

>**In the fast-changing world of Artificial Intelligence (AI), it's crucial to have a smart and flexible way to handle the risks that come with it. The AI Risk Management provides a clear and detailed plan to spot, evaluate, and lessen risks during the entire time AI systems are used. This framework tackles AI-specific issues like figuring out risks, dealing with outside partners, and keeping an eye on new risks as they come up, making sure companies can use AI wisely and safely. It also stresses the importance of being open, responsible, and considering ethical issues, which not only makes AI safer but also builds trust with everyone involved. As AI keeps changing the way we work and live, using a framework like this is key to making the most of AI technologies without running into problems.**
