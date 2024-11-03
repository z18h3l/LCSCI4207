java cAssessment Brief: Individual Coursework
2024–25*~/
Assessment Details
Course Title: Fundamentals of Computer Science I
Course Code: LCSCI4207
Level: 4
First, Second, or Third Sitting: First
Assessment Title: Question Time (Project)
Assessment Number: AE2
Assessment Type: Project
Restrictions on Time/Length: 24 – 32 hours
Assessment Weighting: 40%
Issue Date: 1 October 2024
Hand-in Deadline: 30 October 2024, 13:00
Planned Feedback Deadline: 28 calendar days after hand-in deadline
File Format Accepted: .kts
Mode of Submission: Online (Canvas/Gradescope)
Anonymous Submission: YES
Assessment Task
The setting
You are going to design an application that enables users (in our case, students) to
self-study using a question bank. How does it work?
1. Users will be prompted to choose from a menu of available question banks (e.g.,
Geography, Mathematics, Computing, or History). The selection menu will repeat
until a valid choice is made.
1
Assessment Brief: Individual Coursework 2024–25
2. Users proceed through each question in the selected bank, one-by-one. For each
question, the user is allowed time to reflect; and when they press “Enter”, the
answer is displayed.
3. Users are then asked if they got the correct answer. They self-report by replying
yes or no.
4. After all questions, the program outputs the number of self-reported correct
answers and terminates.
Design overview
You will design this program step-by-step.
Step 1. Questions (6 marks)
Design the data type Question that represents a single question-answer pair. You
should be able to represent the text for the question and the text for the answer.
Include at least three examples – they will come in handy later for tests anyway!
Step 2. Question banks (6 marks)
Design the data type QuestionBank that represents a set of Questions. The bank
should have a name, as well as a sequence of questions. You are encouraged to
represent this sequence using standard lists. Include at least two example question
banks based on the question examples in Step 1.
Step 3. Auto-generated question banks (8 marks)
One benefit of digital question banks is that sometimes we can use code to generate
questions, and their answers, based on a pattern.
Design the function cubes that takes a count (assuming it is positive) and produces a
question bank of that many questions testing the users’ knowledge on perfect cubes
(e.g., 1
3=1, 2
3=8, 3
3=27, and so on). For example, if count equals 4, the four
questions in the bank are:
Q1: What is 1 cubed?
A: 1
Q2: What is 2 cubed?
A: 8
Q3: What is 3 cubed?
A: 27
Q4: What is 4 cubed?
A: 64
Hint 1. You'll find that the List constructor is quite handy!
2
Assessment Brief: Individual Coursework 2024–25
Step 4. Files (16 marks)
Consider a simple format for storing questions in a file. Each Question is a line in
the file, where the question text comes first, separated by a “pipe” character (“|”),
followed by the answer.
4.1. Design the function questionToString that takes a Question as input and
produces a string according to the format above (e.g., “What is the
capital of England?|London”). Make sure to test all your card examples!
4.2. Design the function stringToQuestion that takes a string, assuming that it is
in the format described above, and produces the corresponding Question.
Note 1. No need to remind you about testing anymore, right?
Hint 2. You'll find the Kotlin function String.split(separator) quite handy:
it breaks a string separated by the separator string into a list.
4.3. Design the function readQuestionBank that given a path to a file it produces
the corresponding sequence of cards found in the file. Use whatever
sequence type makes sense for your deck type above. If the file does not
exist, return an empty sequence. Otherwise, you can assume that every line
is formatted as in 4.1 above.
Step 5. Self-reporting on a single question (16 marks)
Let’s work with a single question first, including a user interaction where users
self-report if they got the answer correctly.
5.1. Design the function isCorrect that determines if the supplied string starts
with the letter “y” or “Y”.
Hint 4. The String.startsWith(prefix) function will help you evaluate the
prefix even if the supplied string is too short. The String.lowercase() or
String.uppercase() functions help you not worry about upper- or
lower-case strings, respectively.
5.2. Design the function studyQuestion that uses the Khoury library’s
reactConsole function to: (i) display the question text of the supplied
question; (ii) give the user an opportunity to think (until they press “Enter”);
(iii) display the correct answer; (iv) ask the user to self-report is they thought
of the correct answer; and, finally, (v) provide appropriate feedback.
Step 6. Going over multiple questions (20 marks)
Great job dealing with a single question! Now let's go over an entire question bank
from start to finish:
6.1. Design the data type QuestionBankState to keep track of, at least the
following: (i) which question is currently on display; (ii) whether the user is
3
Assessment Brief: Individual Coursework 2024–25
looking at the question text or the answer; (iii) how many answers have been
self-reported as correct by the user thus far.
Note 2. Create sufficient examples to convince yourself that you can
represent any situation that might arise when going over a question bank.
6.2. Design the function studyQuestionBank that uses reactConsole with your
designed state to go over all the questions in a supplied sequence and returns
the number that were (self-reported) correct.
Step 7. Choosing a bank (20 marks)
Design the function chooseBank that takes a list of QuestionBanks and produces a
corresponding numbered menu (1 for the first question bank, 2 for the second, and
so on), prompts the user for input, and returns the bank corresponding to the number
entered. Make sure you also display the question bank name. For example:
Welcome to Question Time! You can choose from 3 question
banks:
1. Capitals of the World
2. Movies
3: Perfect cubes
Enter your choice:
_
Keep displaying the menu until the user enters a valid number.
Hint 5. mapIndexed behaves like map on a list, but the called function gets both the
index of the current element, as well as the element itself, which can be handy for
producing a numbered menu. The isAnInteger function from the Khoury library
tells you whether a string is an integer, before trying to convert it via
String.toInt().
Step 8. Putting all together (8 marks)
Time for the final app! Design the function play that: (i) uses chooseBank to select
one amongst a list of question banks – the options must include at least one
question bank that you coded by hand, one read from a file (using
readQuestionBank), and one generated by code (e.g., cubes); and (ii) uses
studyBank to go over all the questions in the bank, returning the number of correct
answers.
4
Assessment Brief: Individual Coursework 2024–25
Assessment Criteria
You will be evaluated on several criteria, including: (i) adherence to instructions and
the Fundies 1 coding style guide; (ii) correctly producing the functionality of the
program; (iii) design decisions that include choice of tests; (iv) appropriate
application of list abstractions, and (v) task- and type-driven decomposition of
functions.
70 or higher
There was evidence of the ability to perform all programming tasks correctly. The
demonstration of the methods was excellent, coherent, well documented and clearly
explained.
60-69
There was evidence of ability to perform some programming tasks correctly. The
demonstration of the methods is good, coherent and reasonably detailed and
explained.
50-59
There was evidence of ability to perform some programming tasks correctly, but the
demonstration of the methods was limited, incoherent, not adequately documented
and vaguely explained.
40-49
There was limited evidence of ability to perform programming tasks. The
demonstration of the methods involved significant omissions and produced
substantial inaccuracies.
39 or less
Failure to solve the programming task in assignment. Methods were completely
incorrect or absent. General grading criteria for Level 4 are described in Appendix B
of the course syllabus.
Submitting Assessments
1. Your submission should be anonymous. Remove anything from your code that
can identify you before submission.
2. You are to upload a file question-time.main.kts file on Canvas/Gradescope for
your submission.
3. You are expected to provide necessary documentation for your code. Part of your
marks will be allocated on the quality of your comments!
4. Since mutation has not been covered extensively in class, your program is not
allowed to make use of mutable variables, including mutable lists.
5
Assessment Brief: Individual Coursework 2024–25
5. All interactive parts of your program must make effective use of the
reactConsole function.
6. Staying consistent with our style guide. All functions must have a preceding
comment specifying their purpose and an associated @EnabledTest function with
sufficient tests using testSame.
7. All data must have a preceding comment specifying what it represents and
associated representative examples.
You have three submission attempts, but only the last submission will be graded. If
your last submission attempt is late, you will receive the late penalty even if you have
a previous submission that was on time. Please make sure to avoid multiple
submissions for assessments with multiple components, as only the last attempt will
be graded. Upload several files in one submission attempt instead.
If your assessmen代 写LCSCI4207、Java/Python
代做程序编程语言t requires anonymous submission (see the assessment details
table at the top of your assessment brief), please be sure you have left your name off
of your submission and out of the submission file name, as failing to do so may result
in a 0% mark on the assessment.
Refer to the assessment details table in your assignment brief for acceptable file
formats. Avoid submitting zip files (unless explicitly required by the assessment
brief); use the ‘add files’ function to submit multiple files instead. If you are submitting
a physical artefact, you must also provide clear and thorough documentation (such
as in the form of photographs or a video) of your submission by the deadline; see the
bottom of this section for guidance on submitting video files.
Please ensure that you tick the agreement box at the very bottom of your Canvas
submission page (scroll down if you don’t see it). This will enable you to select
‘Submit Assessment.’ Please review the submitted file to ensure that everything is in
order.
If you encounter any issues with submission, e-mail a copy of your assignment
before the deadline to student.assessments@nulondon.ac.uk along with screenshots
of the problem on Canvas, showing a timestamp.
To turn on notifications for submission confirmation emails in your Canvas settings:
Account > Notifications > Turn on the bell for ‘All submissions.’ In the app this is via
Settings > Email Notifications > All submissions.
To submit a video recording: Select the ‘Panopto video’ icon in the text entry box in
your submission portal. You can upload a video file of any format from your media
library by selecting ‘upload,’ choosing ‘my folder’ in the drop down menu, and
clicking ‘insert.’ You should be able to play the video back once it processes. See
further explanation, including guidance on recording videos using Panopto, in this
support article: ‘How to Submit a Video Assignment in Canvas.’
6
Assessment Brief: Individual Coursework 2024–25
Marking
The University uses two categorical assessment marking schemes – one for
undergraduate and one for postgraduate – to mark all taught programmes leading to
an award of the University.
More detailed information on the categorical assessment marking scheme and the
criteria can be found in the Course Syllabus, available on the University’s VLE.
Learning Outcomes
This assessment will enable students to demonstrate in full or in part the learning
outcomes identified in the Course Descriptor.
On successful completion of this assessment, students should be able to:
Knowledge and Understanding
K1a Demonstrate knowledge and understanding of the underlying principles and
concepts of programming.
K2a Demonstrate knowledge and understanding of program design principles and
concepts such as parametric polymorphism (e.g., generic functions and data
types), generative recursion, and accumulators.
K3a Demonstrate an understanding of the technical, social and management
dimensions of programs, their extensibility and correctness, in real-world
applications.
Subject-Specific Skills
S1a Complete a data analysis of a problem statement and describe the data
required to solve a problem; create input and output examples of the data to
describe the desired functionality of a program that solves the problem at
hand; and use aforementioned examples for testing.
S2a Plan an iterative approach to solve large problems; and design scalable,
abstract data collections to solve growing problems.
S3a Compose programs from several functions and data collections, either
sequentially (e.g., for batch applications) or using event-based features (e.g.,
for web applications).
Transferable Skills
7
Assessment Brief: Individual Coursework 2024–25
T1a Make reasoned discussions and contributions in group settings, fostered
through collaborative work during lab sessions.
T3a Display a developing technical proficiency in written English and an ability to
communicate clearly and accurately in structured and coherent pieces of
writing.
Accessing Feedback
Students can expect to receive feedback on all summative coursework within 28
calendar days of the submission deadline or, if applicable, the last oral assessment
date, whichever later. The 28 calendar day deadline does not apply to work
submitted late. Feedback can be accessed through the assessment link on the
Canvas course page.
Late Submissions
Please ensure that you submit your assignment well before the deadline to avoid
any late penalties, as a submission made exactly on the deadline will be considered
late. Please keep in mind that there may be differences between your computer's
clock and the server time, which can cause discrepancies, and that Canvas may
take some time to process your submission.
Your Canvas submission portal displays two due dates: one is the deadline for your
assignment, and the second is the latest possible date by which your assignment
can be submitted late. Please make sure you submit by the assessment deadline in
order to avoid late penalties.
If assessments are submitted late without approved Extenuating Circumstances,
there are penalties:
● For assessment elements submitted up to one day late, any passing mark
will receive 10 marks deducted or a threshold pass (40% for undergraduate
students, 50% for postgraduate students), whichever is higher. Any mark
below 40% for undergraduate students and below 50% for postgraduate
students will stand.
● Students who do not submit their assessment within one day of the deadline,
and have no approved Extenuating Circumstances, are deemed not to have
submitted and to have failed that assessment element. The mark recorded
will be 0%.
● For assessment subelements, late submission will result in non-submission
penalties deducted according to the marking criteria above.
For further information, please refer to AQF7 Part C in the Academic
Handbook.
8
Assessment Brief: Individual Coursework 2024–25
Extenuating Circumstances
The University’s Extenuating Circumstances (ECs) procedure is in place if there are
genuine circumstances that may prevent a student from submitting an assessment.
If the EC application is successful, there will be no academic penalty for missing the
published submission deadline.
Students are normally expected to apply for ECs in advance of the assessment
deadline. Students may apply for consideration of ECs retrospectively if they can
provide evidence that they could not have done so in advance of the deadline. All
applications for ECs must be supported by independent evidence.
Successful EC applications for live oral assessments, including vivas, will result in a
deferral of the oral to be organised by faculty, students, and Timetabling for a date
as close as possible to the original presentation date. The deadline for
supplementary materials, if assigned, will be carried forward by the length of the oral
assessment extension.
Missing an oral assessment, including a compulsory viva, without an approved EC
will result in a non-submission for the entire assessment and, accordingly, a
recorded mark of 0%.
Students are reminded that the ECs procedure covers only short-term issues (within
21 days leading to the submission deadline) and that if they experience longer-term
matters that impact on learning then they must contact Student Support and
Development for advice.
Under the Extenuating Circumstances Policy, students may defer an assessed
element on only one occasion and may request an extension on a maximum of two
occasions.
For further information, please refer to the Extenuating Circumstances Policy in
the Academic Handbook.
Academic Misconduct
Any submission must be a student’s own work and, where facts or ideas have been
used from other sources, these sources must be appropriately referenced. The
University reserves the right to hold a viva if there are concerns about the
authenticity of a student's or learner’s work. The Academic Misconduct Policy
includes the definitions of all practices that will be deemed to constitute academic
misconduct. This includes the use of artificial intelligence (AI) where not expressly
permitted within the assessment brief, or in a manner other than specified. Students
should check this policy before submitting their work. Students suspected of
committing Academic Misconduct will face action under the Policy. Where students
are found to have committed an offence they will be subject to sanction, which may
include failing an assessment, failing a course or being dismissed from the
University depending upon the severity of the offence committed. For further
information, please refer to the Academic Misconduct Policy in the Academic
Handbook.
9
Assessment Brief: Individual Coursework 2024–25
Version History
Title: Assessment Brief Template
Approved by: The Quality Team
Version
number
Date
approved
Date
published
Owner Location Proposed next
review date
4.0 March
2023
March
2023
Registrar VLE/
Faculty
Resourc
es Page
March 2024
3.0 August
2022
August
2022
Registrar VLE,
Faculty
Resourc
es Page
July 2023
2.3 December
2021
December
2021
Registrar VLE August 2022
2.2 August
2021
August
2021
Registrar VLE August 2022
2.1 Septembe
r 2020
September
2020
Registrar VLE August 2021
2.0 Septembe
r 2020
September
2020
Registrar VLE August 2021
1.0 August
2019
August
2019
Registrar VLE August 2020
Referenced
documents
AQF7 Academic Regulations for Taught Awards; Extenuating
Circumstances Policy; Academic Misconduct Policy; Course
Syllabus
External
Reference
Point(s)
UK Quality Code Theme: Assessment
10

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
