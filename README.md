# AutoProfiler

Utilize the Haystack API to automatically pre-fill some basic info about a user's profile based on his or her profile picture.
__Note:__ this only works on photos containing only one face. 

### Pre-filled fields
- Gender (and confidence score)
- Ethnicity (and confidence score)
- Age

## Installation
Copy `autoprofile.php` into your project directory.

## Usage
```php
$imageData = file_get_contents($_FILES["picture"]["tmp_name"]); 
$autoProfiler = new AutoProfiler("API KEY");
$data = $autoProfiler->getProfileInformation($imageData);
```
### Output
```php
array(
   'gender' => 'female',
   'genderConfidence' => 0.99880000000000002113864638886298052966594696044921875,
   'age' => 53.7000000000000028421709430404007434844970703125,
   'ethnicity' => 'White_Caucasian',
   'ethnicityConfidence' => 0.8973999999999999754862756162765435874462127685546875,
)
```
if the input image is invalid or contains more than one person
```php
null
```