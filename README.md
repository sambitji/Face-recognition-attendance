# Face-recognition-attendance
Student's attendance will be marked by capturing their photos

A.) Overview

This project automates attendance management using artificial intelligence and computer vision. It eliminates manual roll calls, prevents proxy attendance, and ensures accurate record-keeping. The system identifies students through face recognition, marks attendance automatically, and stores the data in both local (MySQL) and cloud (Firebase) databases for reliability and remote access.




B.) Why It’s Necessary

Traditional attendance systems are time-consuming, error-prone, and vulnerable to proxy marking. Institutions require automation that ensures:

Accuracy: Eliminates human and proxy errors.

Speed: Reduces roll-call time drastically.

Integrity: Authenticates presence through unique facial features.

Scalability: Handles large classrooms efficiently.

Cloud Access: Centralized records accessible anytime, anywhere.




C.) System Workflow

1. Face Enrollment

Each student’s face is captured once.
Facial embeddings (numerical patterns of facial features) are generated using deep learning models such as FaceNet or dlib.
These embeddings, along with student details (name, roll number), are stored in:

MySQL (local structured data)

Firebase (cloud database for redundancy)


2. Attendance Capture

When a classroom image or live camera frame is captured:

Faces are detected using OpenCV and face_recognition.

Each detected face is compared with enrolled encodings using Euclidean distance metrics.


3. Automatic Marking

If a match is found within a defined similarity threshold:

Student is marked “Present”.

Attendance record is stored with timestamp in both databases.


4. Data Storage

MySQL: Maintains structured attendance logs for local analytics.

Firebase: Provides remote synchronization and secure backup.




D.) Technologies Used

Python – Core programming language

OpenCV – Face detection and image processing

face_recognition / DeepFace – Deep learning model for facial encoding

NumPy, Pandas – Data manipulation and vector operations

MySQL – Local relational database

Firebase Firestore – Cloud-based database

datetime – Timestamp management




E.) Output

Console-based confirmation of attendance marking (e.g., Marked present: Sambit Sharma (GGSIPU101))

MySQL database entries for each attendance record

Firebase Firestore collection storing synchronized data with timestamps

(Optional extension) GUI or dashboard showing attendance statistics and logs



F.) Benefits

Eliminates manual effort and paper-based tracking.

Prevents fraud or proxy attendance.

Ensures real-time data availability through Firebase synchronization.

Improves classroom efficiency by automating repetitive processes.

Supports analytics — attendance trends, frequency, and student participation can be derived later.



G.) Future Enhancements

Integration with live CCTV or IP cameras for real-time tracking.

Attendance report export to Excel/PDF.

Notification system for absentee alerts.

Web dashboard with role-based access (Admin, Faculty, Student).
