Hackoona Matata- Hackathon
Team Name : CAFFEINE OVERFLOW
Team Members:
S Shakthi - 21i350
Sreenitti S  - 21i360

Problem Statement
Title: Medical AI Assistant for Diagnosis and Preventive Healthcare with Enhanced Privacy Features 
Description: 
In the realm of healthcare, patients often face challenges in obtaining timely insights and accurate diagnoses based on their medical reports such as MRI scans and other diagnostic tests. Additionally, patients seek preventive measures and guidance on potential health risks based on their medical history and symptoms. However, accessing personalized medical advice and recommendations can be cumbersome and time-consuming. The objective of this hackathon challenge is to develop a robust web or app solution that serves as a Medical AI Assistant, providing patients with insightful diagnoses, preventive healthcare measures, and access to relevant medical resources while prioritizing the privacy and security of their sensitive medical records. 
Key Features: 
1. Medical Report Analysis: Utilizes advanced image processing and machine learning to analyze MRI scans and other reports, providing accurate insights into medical conditions and potential risks.
 2. Personalized Recommendations: Offers tailored preventive healthcare measures and lifestyle suggestions based on medical history, symptoms, and risk factors, promoting overall well-being. 
3. Patient History Access: Securely accessing patient medical history using unique IDs, enabling personalized suggestions while ensuring confidentiality.
4. Clinic and Doctor Referrals: Recommends reputable clinics and healthcare providers based on location, medical condition, and preferences, facilitating seamless appointment scheduling. 
5. Transparent AI: Utilizes interpretable machine learning models, providing clear explanations for recommendations to build trust and confidence among users.
6. Blockchain-Based Privacy: Implements blockchain to secure and encrypt medical records, ensuring data integrity and preventing unauthorized access. 
7. Continuous Learning: Incorporates feedback mechanisms to continuously improve diagnostic accuracy and recommendation capabilities over time. 8. Regulatory Compliance: Adheres to healthcare regulations like HIPAA, prioritizing patient confidentiality and privacy.


Literature survey
2.1 Revolutionizing healthcare: the role of artificial intelligence in clinical practice
https://www.researchgate.net/publication/374116437_Revolutionizing_healthcare_the_role_of_artificial_intelligence_in_clinical_practice 
Citation: Alowais, S.A., Alghamdi, S.S., Alsuhebany, N. et al. Revolutionizing healthcare: the role of artificial intelligence in clinical practice. BMC Med Educ 23, 689 (2023). https://doi.org/10.1186/s12909-023-04698-z

This review article provides a comprehensive and up-to-date overview of the current state of AI in clinical practice, including its potential applications in disease diagnosis, treatment recommendations, and patient engagement. It also discusses the associated challenges, covering ethical and legal considerations and the need for human expertise. By doing so, it enhances understanding of AI’s significance in healthcare and supports healthcare organizations in effectively adopting AI technologies.

2.2 Ethical and legal challenges of artificial intelligence-driven healthcare 
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7332220/ 
Citation: Gerke S, Minssen T, Cohen G. Ethical and legal challenges of artificial intelligence-driven healthcare. Artificial Intelligence in Healthcare. 2020:295–336. doi: 10.1016/B978-0-12-818438-7.00012-5. Epub 2020 Jun 26. PMCID: PMC7332220.

This paper discusses four primary ethical challenges that need to be addressed to realize the full potential of AI in healthcare: (1) informed consent to use, (2) safety and transparency, (3) algorithmic fairness and biases, and (4) data privacy. This has been followed by an analysis of five legal challenges in the US and Europe, namely, (1) safety and effectiveness, (2) liability, (3) data protection and privacy, (4) cybersecurity, and (5) intellectual property law. 

2.3 AI in Healthcare: Revolutionizing Patient Care with Predictive Analytics and Decision Support Systems
https://www.researchgate.net/publication/378509213_AI_in_Healthcare_Revolutionizing_Patient_Care_with_Predictive_Analytics_and_Decision_Support_Systems 
Citation: AI in Healthcare: Revolutionizing Patient Care with Predictive Analytics and Decision Support Systems. (2024). Journal of Artificial Intelligence General Science (JAIGS) ISSN:3006-4023, 1(1), 31-37. https://doi.org/10.60087/jaigs.v1i1.p37

This article explores the transformative impact of Artificial Intelligence (AI) in healthcare, with a specific focus on how predictive analytics and decision support systems are revolutionizing patient care. The article also discusses challenges and ethical considerations associated with AI integration in healthcare, emphasizing the importance of responsible deployment and regulatory frameworks. 

2.4 Generative AI in Medical Practice: In-Depth Exploration of Privacy and Security Challenges
https://www.jmir.org/2024/1/e53008#:~:text=Benefits%20and%20Risks-,Overview,toward%20ensuring%20privacy%20and%20security%20%5B 
Citation:  Chen Y, Esmaeilzadeh P
Generative AI in Medical Practice: In-Depth Exploration of Privacy and Security Challenges
J Med Internet Res 2024;26:e53008
URL: https://www.jmir.org/2024/1/e53008
DOI: 10.2196/53008

This study addresses the gap by identifying security and privacy threats and mapping them to the life cycle of various generative AI systems in health care, from data collection through model building to clinical implementation. By identifying and analyzing these threats, we can gain insights into the vulnerabilities and risks associated with the use of generative AI in healthcare. 
Actual Dataset
For image processing:
    Brain MRI Images for Brain Tumor Detection is used for the classification of         the MRI images as Tumor/ Not Tumor.
		About the dataset:
300 images for training and 300 images for testing

	For personalized recommendations:

Medical Transcripts
We leveraged the GPT-3.5 model to generate 4.5k QA prompts from the medical transcripts (MTSamples dataset).
WikiDoc
WikiDoc is a platform for medical professionals to contribute and edit medical content.
10k QnA prompts.
WikiPatient
WikiPatient is a platform for patients to access information and education about diseases.
5K QnA prompts.
	For clinic referrals:
Name : CVS Minute Clinic Data
Source : https://www.kaggle.com/datasets/johndoggodata/cvs-minute-clinic-data
	For driver drowsiness detection and nearby hospital finding : 
Nearby hospital locator : Uses an external API to get location data based on the IP address and does not query a static dataset.

Feature Engineering Pipeline
1. Data Acquisition:
MRI Scans: Securely acquire anonymized MRI scans from patients.
Medical Transcripts: Leverage existing datasets like MTSamples or implement mechanisms for secure medical record access with patient consent.
Location data: Obtained from the ipinfo.io API, which returns JSON data including geographic coordinates and some additional information about the location associated with a given IP address.
Knowledge Bases:
Develop or utilize existing medical knowledge bases like WikiDoc and WikiPatient.
Ensure proper data curation and privacy measures for knowledge base content.
2. Data Preprocessing:
MRI Data:
Preprocessing Techniques:
Skull stripping (remove non-brain tissue)
Intensity normalization
Image registration (align images for comparison)
	Location data( Parsing API Response) : The script processes the JSON response to extract latitude, longitude, city, and state information.

Chatbot Data:
Medical Transcripts:
Clean and normalize text data.
Generate QnA prompts using GPT-3.5 (e.g., from MTSamples).
Knowledge Bases:
Extract relevant information and format it for QnA prompts.
Create QnA prompts from medical knowledge bases.
Privacy Considerations:
Implement strong de-identification techniques for both MRI and text data.
For knowledge bases, ensure informed consent for medical professional contributions.
3. Data Augmentation:
MRI Data:
Apply data augmentation techniques specific to medical images (e.g., elastic deformation, noise injection).
Chatbot Data:
Utilize text data augmentation for QnA prompts (e.g., synonym replacement, paraphrasing).
4. Model Training:
MRI Tumor Detection:
Train a deep learning model (e.g., convolutional neural network) on preprocessed MRI scans for tumor detection and classification.
Medical AI Chatbot:
Fine-tune a large language model (LLM) like Vicuna-13B using LoRA, PEFT, and bitsandbytes with hyperparameters similar to Alpaca.
Utilize LangChain for LLM functionalities, HuggingFace for pre-trained model access, PyTorch for training, all-mpnet-base-V2 for embeddings, and Qdrant for the vector database.
Privacy Considerations:
Explore PPML techniques (e.g., federated learning) for MRI model training to minimize data sharing.
5. Model Evaluation:
MRI Tumor Detection:
Evaluate model performance using metrics like accuracy, sensitivity, and specificity on a separate test set.
Medical AI Chatbot:
Utilize appropriate metrics for QnA tasks (accuracy, F1 score, BLEU score) and consider human evaluation for response quality.
6. User Interaction:
MRI Tumor Detection:
Integrate the model into a secure system for uploading anonymized MRI scans.
Generate reports highlighting tumor detection results and probabilities.
Medical AI Chatbot:
Develop a user interface for patients and medical professionals.
Enable functionalities like:
Patient History Retrieval (secure access to medical records)
Interaction with medical transcripts (ask questions about medical history)
Medical QnA (general medical inquiries)
DocScribe (report summarization, information extraction)
IP-based Geolocation: User's IP address is used to fetch their geolocation.
Privacy Considerations:
Implement robust access control mechanisms for user data.
Allow users control over what information is processed and displayed.
7. Deployment:
Deploy both models on a secure platform with strong data security measures.
Ensure compliance with relevant data privacy regulations (e.g., HIPAA).

Flowchart

ML Model: 
For MRI Tumor Detection: Convolutional Neural Network(CNN)

Convolutional layers : Conv2D for processing two-dimensional data, such as images.
Loss function: Binary Crossentropy
Optimizer: Adam 
	
For Medical AI Chatbot:

LLM(Large Language Model) Components: LangChain
Weights: HuggingFace
Training: PyTorch
Embeddings: all-mpnet-base-V2
Vector database: Quadrant

Expected Outcome and evaluation metrics:
The expected outcome of this integrated medical AI pipeline would be:

For MRI Tumor Detection:

•⁠  ⁠Improved diagnostic accuracy
•⁠  ⁠Early detection
•⁠  ⁠Reduced workload for radiologists

For Medical AI Chatbot:

•⁠  ⁠Enhanced patient education:
•⁠  ⁠Improved communication and decision-making 
•⁠  ⁠Increased efficiency for medical professionals

For finding nearby hospitals: 

•⁠  Accurate detection of driver drowsiness
User location identification
•⁠  Finding nearby hospitals, with name, distance from user location and google maps link
Model Evaluation:
MRI Tumor Detection:
Evaluate model performance using metrics like accuracy, sensitivity, and specificity on a separate test set.
Medical AI Chatbot:
Utilize appropriate metrics for QnA tasks (accuracy, F1 score, BLEU score) and consider human evaluation for response quality.
