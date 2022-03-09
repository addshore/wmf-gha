# wmf-gha

## 2022-03-09

Run using https://integration.wikimedia.org/ci/job/wmf-quibble-selenium-php72-docker/139752 vs https://github.com/addshore/wmf-gha/blob/335753b75ccc6eca7af41249902743061bd22e88/.github/workflows/ci.yml

This is just an updated change (and used docker images) compared with the previous test.

| **Stage**         | **Jenkins** | **Github Actions (no caching)** | Note |
|-------------------|-------------|---------------------------------|------|
| Initial startup         | 37s        | 1s                                | Up until the point we see `Zuul clone with parameters` |
| Fetch Code              | 53s        | 22m 30s                           | |
| Composer Install        | 8s         | 6s                                | |
| Start Backends          | 4s         | 4s                                | |
| Post dependency install | 6s         | 3s                                | The whole of `Run Post-dependency install` |
| Install MediaWiki       | 5s         | 7s                                | |
| NPM Install             | 4m 39s     | 4m 40s                            | Ends at the first line of output relating to browser tests |
| Tests                   | 6m 51s     | 7m 8s                             | only selenium tests! |

## 2021-01-22

Run using https://github.com/addshore/wmf-gha/blob/aac1840d372dabd6860f825526f546552d82e2bd/.github/workflows/ci.yml which matched up to https://integration.wikimedia.org/ci/job/wmf-quibble-selenium-php72-docker/76841

mildly interesting, i ran a wmf-quibble-selenium-php72-docker job that had run on jenkins on github actions just to see what the test execution time was, 23 mins on jenkins, 16 mins on Github Actions https://usercontent.irccloud-cdn.com/file/0HH0fiSK/image.png

| **Stage**         | **Jenkins** | **Github Actions (no caching)** |
|-------------------|-------------|---------------------------------|
| Initial startup   | 48s         | 46s                             |
| Fetch Code        | 47s         | 20m 1s                          |
| Start Backends    | 10s         | 10s                             |
| Install MediaWiki | 4s          | 2s                              |
| Composer Install  | 32s         | 51s                             |
| NPM Install       | 23s         | 19s                             |
| Tests             | 23m 10s     | 16m 3s                          |
