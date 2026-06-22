# User Stories and Acceptance Criteria: Student Task Management System

---

## 1. User Story 1 (US-01)
**Format**: As a Dosen, I want to create a new assignment with a title, description, deadline, and grade weight, so that students receive complete and structured task information.

**Acceptance Criteria**:
- **AC-01.1**: Given a Dosen is on the Create Assignment page, when they fill in all required fields (title, description, deadline, grade weight) and click Submit, then the system saves the assignment and displays it in the student dashboard within 5 seconds.
- **AC-01.2**: Given a Dosen leaves the deadline field empty, when they click Submit, then the system displays an error message "Tenggat waktu wajib diisi" and does not save the assignment.

---

## 2. User Story 2 (US-02)
**Format**: As a Mahasiswa, I want to view a dashboard showing all active assignments with their deadlines and submission status, so that I can prioritize which assignments to complete first.

**Acceptance Criteria**:
- **AC-02.1**: Given a Mahasiswa logs in, when they access the dashboard, then the system displays all active assignments sorted by nearest deadline, showing assignment title, course name, deadline date/time, and submission status (Belum Dikumpulkan / Sudah Dikumpulkan / Terlambat).
- **AC-02.2**: Given a Mahasiswa has no active assignments, when they access the dashboard, then the system displays the message "Tidak ada tugas aktif saat ini" instead of an empty table.

---

## 3. User Story 3 (US-03)
**Format**: As a Mahasiswa, I want to upload my assignment file in PDF or ZIP format and receive a digital receipt, so that I have proof that my submission was received by the system.

**Acceptance Criteria**:
- **AC-03.1**: Given a Mahasiswa uploads a PDF or ZIP file within the deadline, when the upload is complete, then the system displays a success notification with timestamp "Tugas berhasil dikumpulkan pada [tanggal dan jam]" and records the submission in the database.
- **AC-03.2**: Given a Mahasiswa attempts to upload a file with an extension other than .pdf or .zip (e.g., .docx), when they click Upload, then the system rejects the file and displays "Format file tidak didukung. Hanya PDF dan ZIP yang diizinkan."

---

## 4. User Story 4 (US-04)
**Format**: As a Mahasiswa, I want to receive automatic reminder notifications before my assignment deadline, so that I do not miss submission deadlines.

**Acceptance Criteria**:
- **AC-04.1**: Given a Mahasiswa has not submitted an assignment and the deadline is exactly 3 days away, when the scheduled notification job runs, then the system sends a reminder notification (email and/or in-app) to that Mahasiswa containing the assignment title and deadline.
- **AC-04.2**: Given a Mahasiswa has already submitted an assignment, when the H-3 or H-1 reminder is due, then the system does NOT send a reminder notification to that Mahasiswa.

---

## 5. User Story 5 (US-05)
**Format**: As a Dosen, I want to give a numeric grade and written feedback on each student's submission, so that students know their performance and can improve their work.

**Acceptance Criteria**:
- **AC-05.1**: Given a Dosen opens a student's submitted assignment, when they enter a numeric grade (0–100) and written feedback and click Save, then the system saves the grade and feedback and marks the submission as "Dinilai".
- **AC-05.2**: Given a Dosen enters a grade value outside the range 0–100 (e.g., 150 or -5), when they click Save, then the system displays an error "Nilai harus antara 0 dan 100" and does not save the grade.

---

## 6. User Story 6 (US-06)
**Format**: As an Administrator, I want to import user data (lecturers and students) in bulk using a CSV file, so that I can efficiently onboard all users without manual entry.

**Acceptance Criteria**:
- **AC-06.1**: Given an Administrator uploads a valid CSV file following the required format (with columns: NIM/NIDN, Nama, Email, Peran), when the import is complete, then the system creates all valid user accounts and displays a summary "X akun berhasil diimpor, Y baris gagal" with details of failed rows.
- **AC-06.2**: Given an Administrator uploads a CSV file with a missing required column (e.g., Email column is absent), when they click Import, then the system rejects the entire file and displays "Format CSV tidak valid: kolom Email tidak ditemukan" without creating any accounts.

---

## 7. User Story 7 (US-07)
**Format**: As an Administrator, I want to view the system activity log, so that I can audit user actions and ensure data integrity.

**Acceptance Criteria**:
- **AC-07.1**: Given an Administrator navigates to the Activity Log page, when the page loads, then the system displays a paginated table of log entries containing: timestamp, user identity (name + role), action type, and affected object ID, sorted from newest to oldest.
- **AC-07.2**: Given an Administrator applies a filter by date range or action type, when the filter is applied, then the system displays only log entries matching the filter criteria within 3 seconds.
