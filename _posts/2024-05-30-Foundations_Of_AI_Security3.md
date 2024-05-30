---
title: Foundations Of AI Security 3
layout: post
categories: [Notes, AI]
tags: [ai,security,owasp,ml]     # TAG names should always be lowercase
---

<h1><span style="color:Green"> <em>OWASP Machine Learning Top 10</em> </span></h1>

### **1) Input Manipulation Attacks :**

Input Manipulation Attacks refer to a category of attacks where an attacker intentionally modifies the input data to deceive the machine learning model.

Input manipulation attacks map to several techniques in the ATLAS framework, including Evade ML Model, Craft Adversarial Data, and Insert Backdoor Trigger.

To protect machine learning systems from input manipulation attacks, it's essential to adopt a multifaceted defense strategy. Like adversarial training, where the model is exposed to adversarial examples during the training phase. Develop robust models that inherently resist manipulation, this can be achieved through techniques like regularization, and Input validation  that involves scrutinizing incoming data for signs of manipulation

### **2) Data Poisoning Attack :**

Data poisoning attacks involve an attacker deliberately tampering with the training data of a machine learning model. The goal is to introduce errors or biases into the model, leading it to make incorrect predictions or classifications once deployed.

To protect machine learning models from data poisoning attacks, a comprehensive approach that includes various layers of security is crucial. Validation and verification of training data, Securing the storage of training data and Separating training data from production data are vital steps to reduce the risk of compromising the training dataset as well as Regular monitoring and auditing of the training data and Modal validation.

### **3) Model Inversion Attack :**

Model inversion attacks are a type of security threat in which an attacker attempts to reverse-engineer a machine learning model to extract sensitive information embedded within it.

This attack maps to :

- Discover ML Model Ontology (under the "Discovery" tactic)
- Infer Training Data Membership (under the "Exfiltration" tactic, specifically within "Exfiltration via ML Inference API")
- Invert ML Model (under the "Exfiltration" tactic, specifically within "Exfiltration via ML Inference API")
- Craft Adversarial Data (under the "ML Attack Staging" tactic)

To safeguard machine learning models from model inversion attacks, a combination of several preventive measures is needed.  Implementing robust access control mechanisms is crucial. This involves setting up authentication protocols and employing encryption techniques to restrict access to the model and its predictions. Input validation also plays a vital role, alongside Regular monitoring of the model's predictions.

### **4) Membership Inference Attack :**

Membership inference attacks occur when an attacker determines whether a particular data point was used in the training of a machine learning model. By analyzing the model's predictions, attackers can infer the presence of specific data in the training set, potentially exposing sensitive information.

It maps to the "Infer Training Data Membership" sub-technique under the "Exfiltration via ML Inference API" technique.

Training models on randomized or shuffled data.

Model obfuscation (Adding random noise to the model's prediction).

Regularization techniques, such as L1 (Lasso regularization)or L2 (Ridge regularization) regularization.

### **5) Model Theft :**

Model theft attacks happen when an attacker manages to access the parameters of a machine learning model. These parameters are the learned values that the model uses to make predictions, and gaining access to them allows the attacker to replicate or steal the model.

This attack is related to the technique "Extract ML Model" under the Exfiltration tactic.

Encryption, which involves encoding the model's code, training data, and other sensitive information

Access control is another critical defense mechanism.

Regular backups of the model's code, training data, and other sensitive information

Model obfuscation

Watermarking involves embedding a unique identifier into the model's code and training data

Legal protection, such as patents or trade secrets.

Regular monitoring and auditing of the model's use

### **6) AI Supply Chain Attacks :**

AI Supply Chain Attacks are a type of threat that specifically targets the components and processes involved in the development and deployment of machine learning  systems. In these attacks, an adversary seeks to compromise the integrity of ML libraries, models, or associated data used by a system.

This type of attack maps to the ATLAS framework, specifically under the tactic of Initial Access and the technique of ML Supply Chain Compromise.

Implement a comprehensive security strategy that ensures the integrity of machine learning libraries, models, and associated data.

Using secure package repositories and Creating isolated environments

Utilizing package verification tools like PEP 476 and Secure Package Install

### **7) Transfer Learning Attack :**

Transfer learning attacks involve an adversary initially training a machine learning model on one task and then subsequently fine-tuning the model on a different task with the intention of causing the model to behave in a malicious or unintended manner.

It relates to the tactic of ML Attack Staging. Specifically, these attacks can be considered a form of Craft Adversarial Data, where the adversary crafts data or manipulates the learning process to achieve a malicious outcomes.

Regular monitoring and updating of training datasets.

Implementing model isolation by keeping the training environment distinct from the deployment environment.

Conducting regular security audits.

### **8) Model Skewing :**

Model skewing attacks, also known as data distribution attacks, occur when an attacker intentionally manipulates the distribution of the training data to cause the machine learning model to behave in an undesirable manner. In Model Skewing the focus is on altering the distribution of the training data, such as by over-representing or under-representing certain classes or features

This attack maps to the "Poison Training Data" technique under the "Resource Development" tactic.

Implementing robust access controls, Regular auditing of activities, Continuous monitoring of the model's performance and Regularly retraining the model with verified and updated training data.

### **9) Output Integrity Attack :**

In an Output Integrity Attack, an attacker targets the output of a machine learning model with the intention of altering its behavior or inflicting damage on the system where it's deployed. 

This type of attack can be mapped to the ATLAS framework under the "Impact" tactic, specifically the technique “Erode ML Model Integrity”.

Cryptographic methods, such as digital signatures and secure hashes, play a crucial role in verifying the authenticity of the model's results.

Securing communication channels.

Input validation ,by checking the results for any unexpected or manipulated values.

Maintaining tamper-evident logs of all interactions involving inputs and outputs.

Regular software updates and continous monitoring.

### **10) Model Poisoning :**

Model poisoning attacks occur when an attacker directly manipulates the parameters of a machine learning model, causing it to behave incorrectly or produce incorrect results.This type of attack can be particularly insidious because the model may appear to function normally under most circumstances, but it will fail or produce biased results when triggered by specific inputs.

Model poisoning attacks are closely related to the "Backdoor ML Model" technique under the "Persistence" tactic.

One effective strategy in mitigating Model Poisoning is to incorporate regularization techniques, such as L1 or L2 regularization, into the model's loss function.

Designing models with robust architectures and activation functions.

Cryptographic techniques and encryption of the model's parameters and weights.
