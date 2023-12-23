# Mandarin Tone Classification

# Abstract

Learning tonal languages, such as Mandarin Chinese, requires acquiring correct pronunciation and intonation. This project focuses on developing a Natural Language Processing (NLP) model for the classification of Mandarin tones in audio input. The objective is to aid language learners in improving their tonal accuracy and fluency.
The project involves using the Tone Perfect data set as well as feature extraction techniques, including Mel-Frequency Cepstral Coefficients (MFCCs), to represent the tonal characteristics of the input audio [1] .
The NLP model is trained using a Convolutional Neural Network architecture (CNN), optimizing for accuracy in tone classification. The trained model is then applied to real-time audio input data from the user in order to classify their tone.
The potential impact of this project is significant for Mandarin language learners, providing an accessible and interactive tool to enhance their pronunciation skills. By addressing the nuances of tonal variations, the proposed solution aims to accelerate the language learning process and contribute to the broader field of NLP applications for language education. Future work may involve creating a public user-friendly interface for the project, as well as improving the model, with the potential to expand to accommodate regional accents, dialects, and additional features for a more comprehensive language learning experience.

# Introduction
Mandarin Chinese, a tonal language spoken predominantly in China, Taiwan, and Singapore, stands as one of the world's most widely spoken languages. Despite its global prominence and incorporation into educational curricula worldwide, Mandarin poses a formidable challenge for language learners, ranking as a Category 5 difficulty level—the highest classification—by the Foreign Service Institute (FSI) for language learning. Central to the complexity of Mandarin acquisition is its tonal nature, characterized by four distinct tones that critically influence word meanings. While inherent to native speakers, mastering Mandarin tones as a second language learner proves to be a difficult task, often hindering intelligibility.
Presently, the traditional approach to tone acquisition relies heavily on memorization and in-class practice. However, these methods often fall short of cultivating fluent proficiency in tones. The crux of this project lies in proposing a solution to bridge this gap by introducing consistent correction mechanisms during at-home practice sessions. This innovation aims to expedite and enhance the accuracy of Mandarin tone acquisition, thereby offering learners a more efficient pathway to fluency.
Amidst the burgeoning field of language acquisition technology, this project contributes to the discourse by addressing a crucial aspect of Mandarin learning. While not the sole endeavor of its kind, this project strives to elevate the efficacy and precision of existing technologies. The successful development and implementation of an advanced correction mechanism would not only increase access to tonal language learning but also empower learners to achieve greater accuracy in a shorter time frame. As I delve into this project, I anticipate contributing to the evolving landscape of language acquisition technologies and fostering more accessible pathways to proficiency in tonal languages.

# LITERATURE REVIEW!!!!!!

# Methodology/Data Set

Data Set:

This project used the Tone Perfect Data Set, generously provided by Michigan State University. The Tone Perfect Data Set encompasses the comprehensive catalog of monosyllabic sounds in Mandarin Chinese, totaling 410 unique sounds, each articulated in all four distinct tones. With six native Mandarin speakers contributing to this collection (three female and three male), the dataset comprises a total of 9,840 audio files, organized into six sets of 1,640 files each [1]. This data set ensures representation across different speakers and encompasses all possible sound-tone combinations, rendering it an optimal database for training the model.

Visualizations:

Following the data importation into the project notebook, visualizations were executed using all four tones, utilizing the first male voice and the 'ma' sound as exemplars. The ensuing visual representations are presented below:
![Alt Text](<[image-url](https://github.com/lolacmanning/tone_classification/blob/main/First%20Tone%20-%20MFCC%20%231%20Visualization.png)https://github.com/lolacmanning/tone_classification/blob/main/First%20Tone%20-%20MFCC%20%231%20Visualization.png>)






