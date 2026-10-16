# ExamSprint — Google Drive setup

ExamSprint is hosted on GitHub Pages and uses Google Identity Services plus the Google Drive API directly from the browser.

## One-time Google Cloud setup

1. Open Google Cloud Console and create or select a project.
2. Enable **Google Drive API**.
3. Configure **Google Auth Platform / OAuth consent**.
4. Create an **OAuth 2.0 Client ID** with application type **Web application**.
5. Add this Authorized JavaScript origin:
   - https://wasemabujoseph.github.io
6. No client secret is needed in the browser app.
7. Open ExamSprint, expand **Google Drive setup / OAuth Client ID**, paste the Client ID ending in:
   - .apps.googleusercontent.com
8. Click **Save ID**, then **Connect Google Drive**.

If your OAuth app is still in testing mode, add the Google account you will use as a test user.

## Permission used

ExamSprint requests only:

https://www.googleapis.com/auth/drive.file

This grants access to Drive files and folders that the user creates or opens with ExamSprint, instead of requesting full access to all Drive files.

## Storage behavior

- ExamSprint creates a folder named **ExamSprint** in the connected user's My Drive.
- Exams are stored as **.examsprint.json** files.
- Each file keeps:
  - exam title
  - subject
  - original source text
  - parsed questions
  - last-updated time
- The current draft still autosaves locally in the browser for offline use.
- Users can also import/export TXT and JSON without connecting Google Drive.

## Accepted JSON examples

Native ExamSprint package:

```json
{
  "format": "ExamSprint",
  "version": 2,
  "title": "Dermatology Midterm",
  "subject": "Dermatology",
  "sourceText": "Q1: ...\nA) ...\nB) ...\nAnswer: B\nExplanation: ..."
}
```

Generic question-array import:

```json
{
  "title": "Sample",
  "subject": "Dermatology",
  "questions": [
    {
      "question": "Which lesion is fluid filled and >1 cm?",
      "choices": {
        "A": "Papule",
        "B": "Bulla",
        "C": "Macule",
        "D": "Plaque"
      },
      "answer": "B",
      "explanation": "A bulla is a fluid-filled blister larger than 1 cm."
    }
  ]
}
```
