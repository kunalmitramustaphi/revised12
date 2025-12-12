# Doctoral Research Questionnaire

A professional web-based questionnaire platform for doctoral research data collection.

## Features

- **Dynamic Question Loading**: Questions are loaded dynamically from Supabase database
- **Multiple Answer Types**: 
  - Multiple Choice Questions (MCQ) with radio buttons
  - Dropdown selections
  - Text-based answers
- **Progress Tracking**: Visual progress bar showing completion status
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Real-time Validation**: Ensures all required fields are completed
- **Secure Data Storage**: Direct submission to Supabase database

## Tech Stack

- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Backend**: Supabase (PostgreSQL)
- **Hosting**: Vercel

## Database Schema

### question_master Table
Stores all questionnaire questions with the following fields:
- `id`: Primary key
- `question_no`: Question number (unique)
- `question_text`: The actual question
- `answer_options`: Array of options for MCQ/Dropdown
- `answer_type`: Type of answer (mcq, dropdown, text)
- `option_count`: Number of options available

### user_submission Table
Stores participant responses with fields:
- `id`: Unique submission ID
- `created_at`: Timestamp of submission
- `name`, `email`, `gender`, `dob`, `city`: Personal information
- `q1` through `q80`: Answer fields for up to 80 questions

## Setup Instructions

### Prerequisites
- Supabase account with project created
- Git installed on your machine
- GitHub account
- Vercel account

### Local Development

1. Clone this repository
   ```bash
   git clone https://github.com/YOUR_USERNAME/doctoral-questionnaire.git
   cd doctoral-questionnaire
   ```

2. Open `index.html` in your browser to test locally

3. Ensure your Supabase database has:
   - Questions added to `question_master` table
   - Proper RLS (Row Level Security) policies configured

### Deployment

This project is deployed on Vercel. Any push to the main branch will automatically trigger a new deployment.

**Live URL**: [Your deployed URL will appear here after Vercel deployment]

## Configuration

The Supabase connection is configured directly in `index.html`. The anon key is safe to expose as it's protected by Row Level Security policies in Supabase.

## Security

- RLS policies ensure data security
- Anonymous read access for `question_master` table
- Anonymous insert access for `user_submission` table
- All sensitive operations are protected at the database level

## Usage

1. Participants access the questionnaire URL
2. Fill in personal information (name, email, gender, DOB, city)
3. Answer questions one at a time
4. Navigate using Previous/Next buttons
5. Submit the completed questionnaire
6. Receive confirmation message

## Contributing

This is a private research project. If you have suggestions or find issues, please contact the research team.

## License

This project is for academic research purposes. All rights reserved.

## Contact

For questions or support regarding this questionnaire, please contact:
[Your contact information]

## Acknowledgments

Developed for doctoral research at [Your Institution]
