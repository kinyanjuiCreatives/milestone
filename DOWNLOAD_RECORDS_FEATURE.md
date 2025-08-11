# Download Student Records Feature

## Overview
This feature allows users to download student records organized by course in Word document format. The downloaded file includes student names with registration numbers, units, and marks for each unit (CAT 1, CAT 2, END TERM) with missing marks left blank.

## Features

### 1. Course-Based Organization
- Records are organized by course
- All students in the selected course are included
- All units for the course are included as separate rows

### 2. Flexible Filtering
- **Course Selection**: Required - Select which course to download records for
- **Year Filter**: Optional - Filter records by specific year (2021-2025)
- **Term Filter**: Optional - Filter records by specific term (Term 1-4)

### 3. Word Document Format
The downloaded Word document includes:
- Professional header with institution logo
- Course information
- Student Name (Registration Number)
- Units listed vertically for each student
- CAT 1, CAT 2, END TERM scores
- Term and Year information
- Missing marks appear as blank cells
- Summary information (total students and units)

### 4. Missing Data Handling
- If no year/term is specified, the most recent records are included
- Missing marks are left blank in the document
- Students without any records are still included in the file

## How to Use

### Step 1: Access the Feature
1. Navigate to "Download Records" in the main navigation
2. Or click "Download Records" button on the View Records page

### Step 2: Select Parameters
1. **Course**: Select the course you want to download records for (required)
2. **Year**: Optionally select a specific year (optional)
3. **Term**: Optionally select a specific term (optional)

### Step 3: Download
1. Click "Download Word Document" button
2. The file will be downloaded with the format: `{course_name}_student_records.docx`

## Document Format Example

The Word document will contain:

**Header Section:**
- Institution logo/image
- "STUDENT RECORDS BY COURSE" title
- Course information (Course name)

**Table Structure:**
| STUDENT NAME | UNITS | CAT 1 | CAT 2 | END TERM | TERM | YEAR |
|--------------|-------|--------|--------|----------|------|------|
| NJOROGE PETER (MIN\01\4129\24) | DIGITAL LITERACY | 23 | | 48 | 1 | 2024 |
| | COMMON DISEASE | 12 | 23 | 45 | 1 | 2024 |
| | COMMUNICATION SKILLS | | 34 | 12 | 1 | 2024 |
| | ENTERPRENUERSHIP | 23 | 23 | 69 | 2 | 2025 |
| | FIRST AID | 23 | 12 | | 2 | 2025 |
| JOHN EKWAM (MIN\01\4229\24) | DIGITAL LITERACY | 23 | | 48 | 1 | 2024 |
| | COMMON DISEASE | 12 | 23 | 45 | 1 | 2024 |
| | COMMUNICATION SKILLS | | 34 | 12 | 1 | 2024 |

**Summary Section:**
- Total Students: X
- Total Units: Y

## Access Control
- Users must be logged in
- Campus-specific access is enforced
- Superusers can access all campuses
- Regular users can only access their assigned campus

## Technical Details

### View Function
- **File**: `exams/views.py`
- **Function**: `download_student_records_by_course()`
- **URL**: `/download-student-records/`

### Template
- **File**: `templates/exams/download_student_records.html`
- **Features**: Form with course, year, and term selection

### URL Configuration
- **File**: `exams/urls.py`
- **Pattern**: `path('download-student-records/', views.download_student_records_by_course, name='download_student_records_by_course')`

## Benefits
1. **Professional Format**: Word document with proper formatting and styling
2. **Organized Data**: Records are neatly organized with student names and registration numbers
3. **Complete Information**: Includes all students and units for the course
4. **Flexible Export**: Can filter by year and term
5. **Standard Format**: Word format is compatible with Microsoft Word, Google Docs, etc.
6. **Missing Data Handling**: Blank cells for missing marks make it easy to identify gaps
7. **Professional Header**: Includes institution branding and course information
8. **Vertical Unit Listing**: Each unit appears as a separate row for better readability

## Use Cases
- **Academic Reporting**: Generate course-wide performance reports
- **Data Analysis**: Export data for statistical analysis
- **Record Keeping**: Maintain organized student records
- **Parent Communication**: Share organized student performance data
- **Administrative Tasks**: Support administrative decision-making
- **Official Documentation**: Create professional reports for official use 