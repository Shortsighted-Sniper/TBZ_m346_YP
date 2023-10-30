# KN04 screenshots + description

## A) Create picture and host on S3

### Screenshot of the bucket:
<picture>
  <img src="./">
</picture>

### Screenshot of the pictur online:
<picture>
  <img src="./">
</picture>

## B) Adding Web-Server with PHP-site:

### New Cloud-init of the Web-instance:
<picture>
  <img src="./">
</picture>

### Screenshot of image.php:
<picture>
  <img src="./">
</picture>

## C) Adding EBS:

### Screenshot of the EBS of the instance:
<picture>
  <img src="./">
</picture>

## D) Speichereigenschaften erkennen

|                          | Typ  | Persitenz |
|           ---            | ---  |    ---    |
| EBS Root                 | hot  |    nein   |
| EBS Zusätzliches Volumen | warm |     ja    |
| S3                       | cold |     ja    |

### Begründung:

#### 1. Hot Storage:

Hot storage is data that is accessed frequently. This could be data that is being actively used by employees or customers. It needs to be stored on fast storage so that it can be accessed quickly. Is useally has little 

#### 2. Warm Storage:

Warm storage is data that is accessed less frequently. This could be data that is used for reporting or analytics. It doesn’t need to be accessed as quickly as hot data, so it can be stored on slightly slower, capacity-optimized storage.

#### 3. Cold Storage:

Cold storage is data that is rarely accessed. This could be data that is archived for compliance reasons. It can be stored on even slower, “cheap and deep” storage.
