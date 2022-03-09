# wmf-gha

## 2021-01-22

mildly interesting, i ran a wmf-quibble-selenium-php72-docker job that had run on jenkins on github actions just to see what the test execution time was, 23 mins on jenkins, 16 mins on Github Actions https://usercontent.irccloud-cdn.com/file/0HH0fiSK/image.png

| **Stage**         | **Jenkins** | **Github Actions (no caching)** |
|-------------------|-------------|---------------------------------|
| Initial startup?  | 48s         | 46s                             |
| Fetch Code        | 47s         | 20m 1s                          |
| Start Backends    | 10s         | 10s                             |
| Install MediaWiki | 4s          | 2s                              |
| Composer Install  | 32s         | 51s                             |
| NPM Install       | 23s         | 19s                             |
| Tests             | 23m 10s     | 16m 3s                          |
