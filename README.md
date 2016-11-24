# Predicting-Short-Answer-Grades

An NLP project by Avi Dixit and Elizabeth McBride.

## Overview

Over the last two years, data has been collected from over 1000 students who have completed an online curriculum unit on solar ovens. During this curriculum, students learn about science concepts surrounding radiation, conduction, and convection, as well as energy transformation. They are then guided through designing, building, and testing a solar oven. Most of these students are in the 6th grade during the project, but about 150 students were in the 12th grade. In each class, students answer pretest and posttest questions individually. The pretest and posttest are usually the exact same questions, but in some cases one new questions was added on the posttest only.

During the curriculum, one of the most important short response questions asks students to describe their solar oven design and write about how it uses radiation, conduction, and convection. Another question of interest asks students to set goals for their solar oven. Goal setting in this kind of setting can be difficult for students. Many students grasp that they should get their oven to be as hot as possible, but do not articulate specific parameters (how they will test that) or how they might aim to achieve their goal. In addition to the curriculum, we have also implemented “project reports” during the last year of this curriculum. About 500 students (working in pairs or triads) have written project reports (~300-500 words). The project report is a document with pre-generated headers and questions that students complete throughout the project. Section headers are “Designing”, “Building”, “Testing”, etc.

## Project Goals

To make these short response questions more useful for research, it is helpful to code them quickly and accurately. While human scoring would usually be ideal, it is time consuming. There is also a problem of inter-rater reliability, and it takes even more time to ensure different raters are using rubrics in the same way. However, once there is a corpus of responses that has been scored using an agreed-upon rubric, we can develop a way to automatically score these responses. If the responses can be accurately automatically scored, we can also use this scoring to give students feedback in real time to address misconceptions or missing connections. Immediate feedback has been found to be beneficial to student learning in most cases (Kulik & Kulik, 1988), so providing students with immediate feedback or further activities meant to correct misconceptions or gaps in understanding would most likely be beneficial to their learning.

We will try various machine learning methods to find a way to accurately and automatically score the written responses. For the pre- and posttest questions, this will simply involve mapping questions to a 1-5 score. For the questions embedded within the curriculum (formulating goals, description of oven, project reports), this will involve numerical scoring, as well as some analysis of what type of mistake a student might be making.

The process of automatically scoring responses will involve developing features from each question to be used algorithm. We can try using Naïve Bayes, SVM, logistic regression, and random forest models, among others. We have found that in many cases, simple techniques, like using unigram or bigram features, can work extremely well. In reality, more complex methods may not work well on this type of data because the responses were written by middle school students, who are still working on mastering English grammar and language.

Instead of measuring our success based purely on the percent of correctly scored responses, we will also use the measure of Cohen’s kappa. This coefficient measures inter-rater reliability for categorical items. Since the knowledge integration scale functions as more of an ordinal, categorical scheme, though it is numbered, Cohen’s kappa is more appropriate than percent correct. Cohen’s kappa is also an available function in scikit-learn in python. For each question, a Cohen’s kappa value of above 0.80 would be ideal, but 0.75 and above would be acceptable.

For questions embedded within the curriculum, it would be more helpful to understand what students need to improve about their response in order to reach an acceptable level. We generally define an acceptable level as a “4” on the knowledge integration scale. In some cases, students could have misconceptions mixed in with their normative ideas. In other cases, students may be missing some important ideas in their responses. Having an algorithm that can determine what students should do to improve their response would allow us to give more targeted feedback.

In order to find out what students are missing, we would have to first develop a corpus of responses scored in such a way that we are able to tell what is missing and/or incorrect about each response. Once this human coding is completed, we will be able to use similar techniques as those used to automatically score the pre- and posttest questions. 

##Team Member Roles

This data comes from Beth’s dissertation research. Beth will be responsible for coding the pre-/posttest data that was collected in classrooms during October 2016 (schools are finishing the project November 8). Beth will also be organizing the data into a usable format, and developing coding rubrics for the questions embedded within the curriculum. 

We will both work on developing the algorithms for scoring, but will take different approaches. Avi will be responsible for reviewing literature to find other work that may be useful in categorizing student response data.

..........