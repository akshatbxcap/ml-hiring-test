# ML Request Success Prediction Challenge

**Goal:** Build a machine learning model to predict whether a user's request will be successful.

## About the Dataset

This dataset contains user-generated requests from an online community where people post requests seeking help. Each request includes:
- The text content of the request
- Metadata about the user (account age, activity history, karma)
- Whether the request was ultimately successful

Your task is to predict which requests will be successful based on these features.

## Dataset Files

| File | Description |
|------|-------------|
| `data/train.json` | Training data with 3200 labeled examples |
| `data/test.json` | Test data with 800 examples (no labels) |

## Task

1. Build a classifier using `data/train.json`
2. Predict labels for `data/test.json`
3. Submit your predictions in the format below

## Submission Format

Create a CSV file named `submission.csv` with exactly two columns:

```csv
hashed_id,prediction
abc123...,True
def456...,False
```

- `hashed_id`: The unique identifier from the test set
- `prediction`: Your predicted label (`True` = successful, `False` = unsuccessful)

See `sample_submission.csv` for an example format.

## Data Schema

| Field | Type | Description |
|-------|------|-------------|
| `hashed_id` | string | Unique identifier |
| `request_text_edit_aware` | string | Text content of the request |
| `request_title` | string | Title of the post |
| `requester_username` | string | Username |
| `requester_user_flair` | string | User badge |
| `requester_account_age_in_days_at_request` | int | Account age when posting |
| `requester_upvotes_minus_downvotes_at_request` | int | Karma score |
| `requester_number_of_comments_at_request` | int | Total comments by user |
| `requester_number_of_posts_at_request` | int | Total posts by user |
| `requester_number_of_subreddits_at_request` | int | Communities participated in |
| `requester_subreddits_at_request` | list | List of communities |
| `post_was_edited` | bool | Whether post was edited |
| `unix_timestamp_of_request` | int | Timestamp of request |
| `label` | bool | **Target: Was request successful? (train only)** |

## Evaluation

- **Accuracy**: Primary metric
- **Precision/Recall/F1**: Secondary metrics

> **Important Notes:**
> - We will run your code pipeline to **recreate the `submission.csv`** and verify it matches your submitted file. Ensure your code is reproducible!
> - This is a **difficult problem** - we expect accuracy numbers to be relatively low. Don't be discouraged!
> - **We encourage all submissions** if you've put in genuine effort. Your approach and thought process matter as much as the final accuracy.

## Rules

1. **Clone this repository** (do NOT fork - forks are publicly visible)
2. Create your own **new repository** with your solution
3. Any prediction method is allowed as long as you use **open-source tools only**
4. Do not use external data sources to augment predictions
5. Make your repository **public** so we can review your code

## How to Submit

1. Clone this repo: `git clone https://github.com/akshatbxcap/ml-hiring-test.git`
2. Create a new repository on your GitHub account
3. Add your code and generate your `submission.csv` file
4. Push to your new repository
5. Submit via this form: **[Submission Form](YOUR_FORM_URL_HERE)**
   - Include your GitHub repository URL
   - Upload your `submission.csv`
6. **One submission per candidate** - make sure your CSV is correct before submitting!

## Evaluation Criteria

You will be evaluated on:

| Criteria | Description |
|----------|-------------|
| **Model Performance** | Accuracy, Precision, Recall, F1 |
| **Code Quality** | Clean, readable, well-structured code |
| **Approach** | Feature engineering, model selection, experimentation |
| **Your README.md** | You must create a `README.md` in your fork (see below) |

### Required: Create a README.md

Create a `README.md` file in your forked repository that explains:
- Your approach and methodology
- Features you engineered
- Models you tried and why
- Results and insights
- How to run your code

## Tips

- This is an NLP-heavy problem - text fields contain valuable signal
- Class imbalance exists (~25% positive class)
- Feature engineering on user activity metrics can help

Good luck!
