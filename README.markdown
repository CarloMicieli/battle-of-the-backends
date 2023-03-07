# Battle of the Backends

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
![GitHub last commit](https://img.shields.io/github/last-commit/CarloMicieli/battle-of-the-backends)

## Requirements

* Java 17 [sdkman.io/](https://sdkman.io/)
* Rust [rustup.rs/](https://rustup.rs/)
* Git
* Docker

## How to run

```bash
  git clone https://github.com/CarloMicieli/battle-of-the-backends.git
```

### Running a PostgreSQL Database

Run PostgreSQL as a Docker container

```bash
  docker compose up postgres
```

## REST API

|        Endpoint	        |  Method  | Req. body  | Status |  Resp. body  | Description    		                                    |
|:-----------------------:|:--------:|:----------:|:------:|:------------:|:-----------------------------------------------------|
|        `/games`         |  `POST`  |   `Game`   |  201   |              | Add a new game to the catalog                        |
|      `/games/{id}`      |  `PUT`   |   `Game`   |  204   |              | Update the game with the given `{id}`                |
|      `/games/{id}`      |  `GET`   |            |  200   |    `Game`    | Get the game with the given `{id}`                   |
|      `/games/{id}`      | `DELETE` |            |  204   |              | Delete the game with the given `{id}`                |
|      `/platforms`       |  `POST`  | `Platform` |  201   |              | Add a new platform to the catalog                    |
|    `/platforms/{id}`    |  `PUT`   | `Platform` |  204   |              | Update the platform with the given `{id}`            |
|      `/platforms`       |  `GET`   |            |  200   | `Platform[]` | Get all platforms in the catalog                     |
|    `/platforms/{id}`    |  `GET`   |            |  200   |  `Platform`  | Get the platform with the given `{id}`               |
| `/platforms/{id}/games` |  `GET`   |            |  200   |   `Game[]`   | Get all games for the platform with the given `{id}` |

## Conventional commits

This repository is following the conventional commits practice.

### Enforcing using git hooks

```bash
  chmod +x .githooks/commit-msg
  git config core.hooksPath .githooks
```

The hook itself can be found in `.githooks/commit-msg`.

### Using Commitizen

Install [commitizen](https://github.com/commitizen-tools/commitizen)

```bash
  pip install commitizen
```

and then just use it

```bash
  cz commit
```

## License

[Apache 2.0 License](https://choosealicense.com/licenses/apache-2.0/)

```
   Copyright 2023 Carlo Micieli

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```
