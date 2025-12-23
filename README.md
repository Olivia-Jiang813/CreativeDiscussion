# CreativeDiscussion Dataset

A multi-level dataset for studying collaborative creative problem-solving, combining individual characteristics, discourse processes, and creativity outcomes.

## Dataset Statistics

| Metric | Value |
|--------|-------|
| Discussions | 309 |
| Teams | 103 |
| Participants | 421 |
| Utterances | 36,223 |
| Team sizes | 3-person and 6-person |
| Tasks | 6 creative problem-solving scenarios |

## Files

### utterances.csv
Utterance-level discourse annotations (36,223 rows).

| Column | Type | Description |
|--------|------|-------------|
| `group_id` | int | Team identifier |
| `task` | str | Task ID (PS1-PS6) |
| `n_members` | int | Team size (3 or 6) |
| `start_time` | float | Start time (seconds) |
| `end_time` | float | End time (seconds) |
| `duration` | float | Duration (seconds) |
| `speaker_id` | int | Speaker (1 to n_members) |
| `text` | str | Transcribed utterance |
| `discourse_label` | str | Discourse function code |
| `idea_label` | str | Idea identifier (if applicable) |
| `in_final_answer` | bool | Whether idea was adopted |

**Discourse Labels:**
| Code | Definition |
|------|------------|
| GEN | Introduces a new actionable idea |
| ELAB | Elaborates on an existing idea |
| EVAL | Evaluates an idea's merit |
| SUM | Summarizes earlier content |
| FRAM | Frames or clarifies the task |
| META | Manages process, roles, timing |
| OTHER | Fillers, off-topic, fragments |

### participants.csv
Individual-level characteristics (421 rows).

| Column | Type | Description |
|--------|------|-------------|
| `participant_id` | str | Unique participant ID |
| `group_id` | int | Team identifier |
| `age` | int | Age in years |
| `gender` | str | Gender |
| `ethnicity` | str | Ethnic background |
| `employment` | str | Employment status |
| `level_of_education` | str | Education level |
| `location` | str | Geographic region |
| `discipline` | str | Academic discipline |
| `area_of_work` | str | Work domain |
| `work` | int | Years of work experience |
| `language` | str | English proficiency |
| `language2` | str | Other languages |
| `agreeableness` | float | Big Five (1-5) |
| `conscientiousness` | float | Big Five (1-5) |
| `extraversion` | float | Big Five (1-5) |
| `neuroticism` | float | Big Five (1-5) |
| `openness` | float | Big Five (1-5) |
| `perceived_creativity` | float | Self-rated team creativity |
| `time_perception` | float | Perceived time adequacy |
| `number_perception` | float | Perceived team size adequacy |
| `effort` | str | Self-reported effort level |
| `role` | str | Self-identified role |
| `relationship_importance` | float | Relationship importance rating |
| `feedback_importance` | float | Feedback importance rating |

### discussions.csv
Discussion-level metadata and outcomes (309 rows).

| Column | Type | Description |
|--------|------|-------------|
| `group_id` | int | Team identifier |
| `task` | str | Task ID (PS1-PS6) |
| `team_size` | int | Number of participants |
| `creativity` | float | Overall creativity (0-1) |
| `novelty` | float | Novelty rating (0-1) |
| `usefulness` | float | Usefulness rating (0-1) |
| `pattern` | str | Discussion pattern |
| `final_idea` | str | Submitted solution text |

**Discussion Patterns:**
- Divergent–Convergent Funnel
- Parallel Pathways
- Early Anchor & Deep Dive
- Sequential Replace
- Brainstorming without Evaluation

## Tasks

| ID | Topic | Description |
|----|-------|-------------|
| PS1 | Plastic Pollution | Reduce plastic pollution |
| PS2 | Supply Chain | Tackle supply chain security |
| PS3 | Sorry Pandemic | Reduce fictional pandemic spread |
| PS4 | Education Inequality | Overcome education inequality |
| PS5 | Employee Attrition | Stop voluntary employee attrition |
| PS6 | Shower Singing | Encourage healthy shower singing |

## Data Linkage

```
participants.csv ──── group_id ──── discussions.csv
                          │
                          └──────── utterances.csv
                                    (group_id + task)
```
