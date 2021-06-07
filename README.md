# Karenina
Karenina Emotion Analysis Dataset

## Karenina dataset

The Karenina dataset is released in the JSON lines (JSONL) format.

### Karenina data fields

1.  `text` (str): the example sentence. This is the text that was presented to annotators.
2.  `id` (str): unique identifier for this example
3.  `labels` (list): inferred labels from underlying annotations. 
4.  `scores` (dict): probability distribution across emotions based on underlying annotations.
5.  `annotations` (list of dicts): list of raw annotations from workers. Each annotation is represented as a dictionary with:
     * `annotator_id` (str): the anonymized ID of the worker
     * `tags` (list): the selected tags from this worker for this example
6. `annotation_count` (int): total number of tags selected by workers for this example
7. `label_count` (int): total number of inferred labels for this example
8. `review_metadata` (dict): metadata from the review from which the example sentence originated
    * `review_id` (str): unique identifier for the review
    * `user_id` (str): unique identifier for the author of the review
    * `business_id` (str): unique identifier for the business the review is about
    * `stars` (float): the review rating, i.e., the number of `stars` (1-5) the user assigned to the business in the review 
    * `useful` (float): number of `useful` votes this review received from other users
    * `funny` (float): number of `funny` votes this review received from other users
    * `cool` (float): number of `cool` votes this review received from other users
    * `date` (str): date and time the review was posted
    * `sentence_offset` (int): the offset of the sample `text` in the original review

## Karenina sample document

Each example in the Karenina dataset includes the example text, the underlying annotations from annotators, scores and inferred labels based on the annotations, and metadata from the review from which the example sentence originated.

Sample document:
```
{
 'text': 'She said, "oh did I just hit you?"',
 'id': '21cd2dec-e935-4ce4-aba0-6851941b229d',
 'labels': ['confused', 'frustrated', 'disappointed'],
 'scores': {
    'angry': 0.05,
    'disappointed': 0.25,
    'frustrated': 0.25,
    'stressed': 0.1,
    'worried': 0.0,
    'neutral': 0.05,
    'positive': 0.0,
    'confused': 0.3
 },
 'annotations': [
  {'annotator_id': 'A63', 'tags': ['stressed', 'angry']},
  {'annotator_id': 'A35', 'tags': ['frustrated', 'disappointed']},
  {'annotator_id': 'A151', 'tags': ['confused', 'frustrated']},
  {'annotator_id': 'A248', 'tags': ['confused', 'stressed']},
  {'annotator_id': 'A180', 'tags': ['confused', 'disappointed']},
  {'annotator_id': 'A268', 'tags': ['frustrated', 'other negative emotion']},
  {'annotator_id': 'A1', 'tags': ['disappointed', 'frustrated']},
  {'annotator_id': 'A34', 'tags': ['disappointed', 'frustrated']},
  {'annotator_id': 'A162', 'tags': ['neutral', 'confused']},
  {'annotator_id': 'A347', 'tags': ['confused', 'disappointed']},
  {'annotator_id': 'A370', 'tags': ['confused', 'other negative emotion']}
 ],
 'annotation_count': 22,
 'label_count': 3,
 'review_metadata': {
  'review_id': '7HpRNHYZE7YPxy6Z_80CTQ',
  'user_id': '2mVIFFgVLdCMbkuiAF0stQ',
  'business_id': 'Qh477Dag_gSdzaILyECpvg',
  'stars': 1.0,
  'useful': 4.0,
  'funny': 0.0,
  'cool': 0.0,
  'date': '2018-04-19 19:18:26',
  'sentence_offset': 216
 }}
```
