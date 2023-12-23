# Mandarin Tone Classification

# Abstract

Learning tonal languages, such as Mandarin Chinese, requires acquiring correct pronunciation and intonation. This project focuses on developing a Natural Language Processing (NLP) model for the classification of Mandarin tones in audio input. The objective is to aid language learners in improving their tonal accuracy and fluency.
The project involves using the Tone Perfect data set as well as feature extraction techniques, including Mel-Frequency Cepstral Coefficients (MFCCs), to represent the tonal characteristics of the input audio [3] .
The NLP model is trained using a Convolutional Neural Network architecture (CNN), optimizing for accuracy in tone classification. The trained model is then applied to real-time audio input data from the user in order to classify their tone.
The potential impact of this project is significant for Mandarin language learners, providing an accessible and interactive tool to enhance their pronunciation skills. By addressing the nuances of tonal variations, the proposed solution aims to accelerate the language learning process and contribute to the broader field of NLP applications for language education. Future work may involve creating a public user-friendly interface for the project, as well as improving the model, with the potential to expand to accommodate regional accents, dialects, and additional features for a more comprehensive language learning experience.

# Introduction

Mandarin Chinese, a tonal language spoken predominantly in China, Taiwan, and Singapore, stands as one of the world's most widely spoken languages. Despite its global prominence and incorporation into educational curricula worldwide, Mandarin poses a formidable challenge for language learners, ranking as a Category 5 difficulty level—the highest classification—by the Foreign Service Institute (FSI) for language learning. Central to the complexity of Mandarin acquisition is its tonal nature, characterized by four distinct tones that critically influence word meanings. While inherent to native speakers, mastering Mandarin tones as a second language learner proves to be a difficult task, often hindering intelligibility.
Presently, the traditional approach to tone acquisition relies heavily on memorization and in-class practice. However, these methods often fall short of cultivating fluent proficiency in tones. The crux of this project lies in proposing a solution to bridge this gap by introducing consistent correction mechanisms during at-home practice sessions. This innovation aims to expedite and enhance the accuracy of Mandarin tone acquisition, thereby offering learners a more efficient pathway to fluency.
Amidst the burgeoning field of language acquisition technology, this project contributes to the discourse by addressing a crucial aspect of Mandarin learning. While not the sole endeavor of its kind, this project strives to elevate the efficacy and precision of existing technologies. The successful development and implementation of an advanced correction mechanism would not only increase access to tonal language learning but also empower learners to achieve greater accuracy in a shorter time frame. As I delve into this project, I anticipate contributing to the evolving landscape of language acquisition technologies and fostering more accessible pathways to proficiency in tonal languages.

# Literature Review

The 2023 research conducted by Yan et al. explores recent advancements in Mandarin tone recognition, critically evaluating state-of-the-art methods such as ToneNet and CNN. ToneNet, despite achieving an impressive accuracy of 99.16% on the SCSC database, is highlighted for its dependency on extensive data and complex calculations, rendering it less suitable for deployment on small mobile terminals. Interestingly, the CNN method employed in the study did not consistently outperform the proposed approach. Taking into account operational time and computational complexity, the method presented in this research emerges as the most cost-effective alternative.
This research makes a significant contribution to the field by introducing a cost-effective and robust Mandarin tone recognition approach. As language learning applications increasingly incorporate technological advancements, the proposed method holds the potential to facilitate more accessible and accurate Mandarin language acquisition. The study underscores the transformative impact that advanced algorithms can have on language education, providing a pathway for practical implementation on learning terminals [7].

The 2016 study conducted by Chen et al. delves into the critical issue of tone perception in languages, with a specific focus on challenging listening conditions, particularly in children with cochlear implants who often face deficiencies in tone development. The primary objective of the study is to establish an automated method for evaluating tone-production accuracy in these children. The proposed method presents a fully automated approach to tone classification for Mandarin Chinese syllables, utilizing convolutional neural networks (CNN). The results of the study showcase significantly higher accuracy, underscoring the effectiveness of the CNN-based approach. In future research endeavors, the authors plan to extend the evaluation to continuous speech, allowing for the inclusion of co-articulation features. These features have demonstrated promise in enhancing accuracy in prior studies. Overall, this work lays a solid foundation for a robust and automated system that holds the potential to significantly benefit the assessment of tone production in hearing-impaired individuals, addressing a pressing need in the field [4].

Both these studies show case that the CNN model has very good attributes, which make it the model I would like to rely on with this research. The first provides a good foundation of what I want to look at, and is from where this technology should build. The second study is interesting as it again uses CNN, which provides me with insight into this model, but has a different focus than this project.

# Methodology/Data Set

Data Set:

This project used the Tone Perfect Data Set, generously provided by Michigan State University. The Tone Perfect Data Set encompasses the comprehensive catalog of monosyllabic sounds in Mandarin Chinese, totaling 410 unique sounds, each articulated in all four distinct tones. With six native Mandarin speakers contributing to this collection (three female and three male), the dataset comprises a total of 9,840 audio files, organized into six sets of 1,640 files each [3]. This data set ensures representation across different speakers and encompasses all possible sound-tone combinations, rendering it an optimal database for training the model.

Visualizations:

Following the data importation into the project notebook, visualizations were executed using all four tones, utilizing the first male voice and the 'ma' sound as exemplars. The ensuing visual representations are presented below:

First Tone

![Visualization 1 MFCC #1](visualizations/First%20Tone%20-%20MFCC%20%231%20Visualization.png)
![Visualization 1 MFCC #2](visualizations/First%20Tone%20-%20MFCC%20%232%20Visualization.png)
![Visualization 1 Waveform](visualizations/First%20Tone%20-%20Waveform%20Visualization.png)

Second Tone

![Visualization 2 MFCC #1](visualizations/Second%20Tone%20-%20MFCC%20%231%20Visualization.png)
![Visualization 2 MFCC #2](visualizations/Second%20Tone%20-%20MFCC%20%232%20Visualization.png)
![Visualization 2 Waveform](visualizations/Second%20Tone%20-%20Waveform%20Visualization.png)

Third Tone

![Visualization 3 MFCC #1](visualizations/Third%20Tone%20-%20MFCC%20%231%20Visualization.png)
![Visualization 3 MFCC #2](visualizations/Third%20Tone%20-%20MFCC%20%232%20Visualization.png)
![Visualization 3 Waveform](visualizations/Third%20Tone%20-%20Waveform%20Visualization.png)

Fourth Tone

![Visualization 4 MFCC #1](visualizations/Fourth%20Tone%20-%20MFCC%20%231%20Visualization.png)
![Visualization 4 MFCC #2](visualizations/Fourth%20Tone%20-%20MFCC%20%232%20Visualization.png)
![Visualization 4 Waveform](visualizations/Fourth%20Tone%20-%20Waveform%20Visualization.png)


After visualizing the data, the next step involved organizing the dataset by tone and transforming the audio recordings from MP3 format to Mel-Frequency Cepstral Coefficients (MFCC). MFCCs are particularly well-suited for various machine learning tasks, including speech recognition and music analysis, as they effectively capture the spectral characteristics of sound [5].
Subsequently, the data underwent preprocessing to ensure it was ready for analysis. A comprehensive dataset was then constructed to serve as the foundation for training the models.
The initial model applied to the dataset was Support Vector Machines (SVM), a powerful algorithm known for its efficacy in pattern recognition. SVM utilizes kernel mapping functions to project the input data into a higher-dimensional space, aiming to find the optimal hyperplane for the best separation of classes [6]. The SVM model exhibited impressive performance, consistently achieving an accuracy exceeding 97% when tested on the original dataset.
The second model employed was a Convolutional Neural Network (CNN), an advanced deep learning method specifically designed for multiclass classification in speech signal recognition [5]. The CNN model proved highly effective, delivering an accuracy surpassing 99%. Given its outstanding performance, this model was selected for further use and subsequently saved for application to the input data.

# Results

After successfully training the model, the subsequent challenge involved obtaining real-time audio input for model testing. This proved to be the most intricate phase of the process, leading me to be inspired by code used by tayburke, someone doing a similar project with a audio recording component [2]. Once the audio data was captured, I devised a function to convert the MP3 files into MFCCs and subsequently applied the trained model to predict the most likely tone.
Given the nature of self-recorded audio, discerning strict patterns or quantifiable percentages posed a challenge. However, a notable observation was that the model tended to predict 'Tone 4' more frequently than other tones. While there was some accuracy in the predictions, there remains room for improvement. A primary challenge lies in assessing the recording quality and understanding how it differs from the input set, making it an aspect warranting further refinement.

# Discussion

The research motivation behind this project was to contribute to the advancement of technology designed to enhance tonal language acquisition through real-time evaluation of a speaker's tone. The progress made in this direction has resulted in the development of a foundational model for this innovative concept. Prior research within this domain has demonstrated significant advancements, and as the field of tonal language support continues to evolve, opportunities for improvement and expansion become increasingly apparent.
Numerous models have been employed for Mandarin tone classification, with Convolutional Neural Networks (CNN) emerging as a successful choice. In this project, CNN was selected due to its compatibility with Mel-Frequency Cepstral Coefficients (MFCCs) and its effectiveness in tonal classification. 
Ongoing research is revealing intriguing approaches, including the utilization of Random Forest, Feature Fusion, and Deep Neural Networks (DNN). While there is room for enhancement in the current model and others within the field, the persistent pursuit of this technology is essential for advancing tonal language acquisition.
Despite the progress, challenges remain in real-time audio input for model testing. Using code from tayburke’s project was very helpful for the aspect of recording data, as doing this on my own was proving very challenging, especially on an older computer [2]. While some accuracy was observed, the difficulty lies in assessing recording quality and understanding its variance from the input set, requiring further refinement.
In the broader context, the importance of technology facilitating language learning extends beyond education. It has the potential to transform cross-border communication from an occasional occurrence to a commonplace reality, fostering increased cooperation and empathy across borders.
In an era marked by heightened prejudices and a perceived global disconnect, the ability to communicate with individuals from diverse backgrounds is paramount. This technological advancement becomes particularly significant amid strained relations between nations, such as the US and China, highlighting the urgency of effective communication between citizens.

# Conclusion

The research, driven by the goal of enhancing tonal language acquisition, has demonstrated the effectiveness of utilizing Convolutional Neural Networks (CNN) to recognize patterns in the Mel-Frequency Cepstral Coefficients (MFCC) of Mandarin tones for classifying user-input speech. The findings underscore the potential of this technology to reshape the landscape of tonal language acquisition and enhance accessibility to language learning. Through ongoing development and further research into optimal methodologies, this technological advancement holds the promise of transforming the field, ultimately contributing to improved cross-border communication.

# References

[1]Alsobhani, Ayad et al 2021 J. Phys.: Conf. Ser. 1973 012166 

[2]Burke, Taylor,  Learning Tones, (2020), GitHub repository, https://github.com/tayburke/Learning-Tones/blob/master/LearningTones.ipynb 

[3]Catherine Ryu, Mandarin Tone Perception & Production Team, and Michigan State University Libraries. Tone Perfect: Multimodal Database for Mandarin Chinese. Accessed 1 January 2022. https://tone.lib.msu.edu/ 

[4]Chen, Charles & Bunescu, Razvan & Xu, Li & Liu, Chang. (2016). Tone Classification in Mandarin Chinese Using Convolutional Neural Networks. 10.21437/Interspeech.2016-528. 

[5]Kiran, U. (2023, August 14). MFCC technique for speech recognition. Analytics Vidhya. https://www.analyticsvidhya.com/blog/2021/06/mfcc-technique-for-speech-recognition/ 

[6]Mansour, A., & Lachiri, Z. (2017). SVM based emotional speaker recognition using MFCC-SDC features. International Journal of Advanced Computer Science and Applications, 8(4). https://doi.org/10.14569/ijacsa.2017.080471

[7]Yan J, Meng Q, Tian L, Wang X, Liu J, Li M, Zeng M, Xu H. A Mandarin Tone Recognition Algorithm Based on Random Forest and Feature Fusion †. Mathematics. 2023; 11(8):1879. https://doi.org/10.3390/math11081879

