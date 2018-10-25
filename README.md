


**************************************************************************************************
**THIS IS AN UNOFFICIAL IMPROVED VERSION FOR M2Scorer**     
****************************************************************************************************

Compared to [the original M2 scorer](https://github.com/nusnlp/m2scorer), this script can (1) evaluate GEC system faster, (2) process sentences in parallel, and (3) show each sentence-level score.

### Contents  
1. Quickstart
2. Pre-requisites
3. Using the scorer   

### Quickstart

```
./m2scorer [-v] SYSTEM SOURCE_GOLD
```
SYSTEM = the system output in sentence-per-line plain text.
SOURCE_GOLD = the source sentences with gold edits.

### Pre-requisites
The following dependencies have to be installed to use the M^2 scorer.

* Python (>= 2.6.4, < 3.0, older versions might work but are not tested)
* nltk (http://www.nltk.org, needed for sentence splitting)
* **joblib (https://pypi.org/project/joblib/, needed for parallel computing)**
* **numpy (http://www.numpy.org/)**

### Using the scorer
```
Usage: m2scorer [OPTIONS] SYSTEM SOURCE_GOLD
```
where   
 SYSTEM          -   system output, one sentence per line   
 SOURCE_GOLD     -   source sentences with gold token edits   
```
OPTIONS
  -v    --verbose             -  print verbose output
  --very_verbose              -  print lots of verbose output
  --max_unchanged_words N     -  Maximum unchanged words when extracting edits. Default = 2.
  --ignore_whitespace_casing  -  Ignore edits that only affect whitespace and casing. Default no.
  --beta                      -  Set the ratio of recall importance against precision. Default = 0.5.
  --parallel N                -  The maximum number of concurrently running jobs. Default = 1
  --joblib_verbose N          -  joblib.Parallel() 's verbosity level. Default = 0.
  --sentnece_level            -  Print sentence-level scores, not a corpus-level score.
```
