# HairSplittingModel
 A simple Deep Learning model for point clusterizattion
 
 Abstract

This paper focuses on the development of medical
software for clinical applications using advanced image processing algorithms.

Three critical issues of hair segmentation and
counting are addressed in this paper. First, the removal of any
bright spots due to oil or moisture, which generate circular
patterns in the middle of the hair and significantly affect the
accuracy of determining the line. Second, two contacting or
overlapping hairs are recognized and counted as a single hair.
To solve this problem, we proposed a hair-bundling algorithm to
calculate any concealed hairs. Finally, hairs may be wavy or curly,
making the conventional Hough-based line detection algorithm
unsuitable, since it suffers from parameter selections, such as
the minimum length of line segment, and distance between line
segments. Our proposed hair counting algorithm is substantially
more accurate than the Hough-based one, and robust to curls,
oily scalp, noise-corruption, and overlapping hairs, under various
white balance.

Index Terms— Hair counting, scalp diagnosis, hair care

diagnosis, hair follicle diagnosis, line segment detection.


I. INTRODUCTION

BIOMEDICAL image processing plays an important role
in improving the accuracy of medical and cosmetic applications. An accurate medical image allows a doctor to make a
more informed decision regarding the treatment of his patient.
The image processing technology substantially improves the
fields of health and medicine. For example, when investigating
hair and scalp conditions are due to living in a different climate
zone, age, or gender, image processing technology can be
applied in both scalp and skin examinations to provide an
accurate diagnosis. Furthermore, household pets are becoming
increasingly common in modern society, and pet hair loss is
a major issue for many pet owners. Modern image processing
technology can also be of benefit in the field of veterinary
medicine. The advances in digital image processing technology allows for computer-aided diagnosis and treatment that is
capable of dealing with computed tomography (CT), positron
emission tomography (PET), cardiovascular, ultrasound, and
X-ray images.


Manuscript received September 4, 2014; revised December 3, 2014;
accepted December 3, 2014. Date of publication December 18, 2014; date
of current version May 4, 2015. This work was supported by the Ministry
of Science and Technology of Taiwan under Grant MOST103-2221-E-155-
027-MY2 and Grant NSC102-2221-E-155-037-MY2. The associate editor
coordinating the review of this paper and approving it for publication was
Dr. Anna G. Mignani.
The author is with the Human-Computer Interaction Multimedia Laboratory,
Innovation Center for Big Data and Digital Convergence, Department of
Electrical Engineering, Yuan Ze University, Zhongli 320, Taiwan (e-mail:
hcshih@saturn.yzu.edu.tw).
Color versions of one or more of the figures in this paper are available
online at http://ieeexplore.ieee.org.
Digital Object Identifier 10.1109/JSEN.2014.2381363


A. Related Work
Most research topics for hair image processing usually focus
on hair modeling, creating a synthesis, and an animated global
view. For instance, Mao et al. [1] presented a method for generating a realistic human hair texture. Chen and Zhu [2] proposed a generative model for synthesizing realistic hair images
from a stylistic drawing or sketch. It is based on the global hair
style regardless of the congenital hair flow for the purpose of
hair editing and hair rendering. Yacoob and Davis [3] developed computational models for measuring hair appearance
using a multidimensional representation for human identification and hairstyle retrieval. An example-based hair geometry synthesis appeared in [4]. For hair shape modeling,
Wang et al. [5] presented a part-based model that was robust
to both hair shape and variations in the environment. The
so-called subspace clustering dependency guarantees a reasonable output and allows for evaluating the effectiveness of
part-wise constraints in an information-theoretic way. In recent
years, a number of articles on hair-region segmentation and
modeling appeared [6]–[8].
Regarding fine hair, medical image analyses have been
focused mainly on pigmented skin lesion images for hair
removal [9]–[11] and border detection [12]–[14]. Research
literature has been focused mainly on hair segmentation and
removal because the hairs are an obstacle for the clinical
diagnosis of the scalp. Huang et al. [15] evaluated a hair
removal software, DullRazor [16], and proposed conventional
matched filters to enhance the curvilinear structures and
improve the detection of thin hairs and hairs in shadow.
The authors also demonstrated that missing hair intersections
can be recovered by applying regional growing algorithms
with a color-similarity criteria. However, these aforementioned
techniques do not take into consideration the condition of the
hairs such as their health condition, density, diameter, oiliness,
nor the number of hairs on each single follicle.
