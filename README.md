# Vitaes

![api](https://github.com/NeverDefineUs/vitaes/workflows/api/badge.svg)
![logger](https://github.com/NeverDefineUs/vitaes/workflows/logger/badge.svg)
![renderer](https://github.com/NeverDefineUs/vitaes/workflows/renderer/badge.svg)
![storage](https://github.com/NeverDefineUs/vitaes/workflows/storage/badge.svg)
![webapp](https://github.com/NeverDefineUs/vitaes/workflows/webapp/badge.svg)

## The Project
Vitaes is an open source tool with the purpose of making the curriculum creation process easier.
It uses an abstract tree to model the curriculum and compiles it in a PDF.

## Requirements
To work with this project you will need:
- docker-compose
- python3 (used to run scripts and possibly renderer)
- node/npm (optional. Get it to run webapp without docker)
- golang (optional. Get it if you plan to make big changes on any of the golang services. Used v1.12.4)

##### Production only requirements
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- [kubectl-aliases](https://github.com/ahmetb/kubectl-aliases) (**PLEASE READ CAREFULY**)
- [linkerd](https://linkerd.io/2/getting-started/)
- [doctl](https://github.com/digitalocean/doctl)

## Running the project

Following scripts available (on project root):
- `python scripts/init.py` (first time on environment only)
- `python scripts/build.py`
- `python scripts/push.py` (production only)
- `python scripts/start.py`

To stop, run `python scripts/kill.py`

You can choose the environment to run the script by adding `--prod`(`-p`) or `--staging`(`-s`) to the command. (defaults to development without any options)

You should be using python 3.

### Development

In the development flow, you should only run the init script once and them start and kill. There's no need to run the build script in development, since start will build when necessary. (will build everything on first run)

After running start script, all containers will be running. (it might take up to a minute for full start)
Run `docker ps` to see information from the containers.

When the containers are running, access the app through your browser at `http://localhost/`.

## Contributing
You can fork and make a pull request at anytime, fixing an issue or adding a feature you think would be useful.

## Releases
Releases are made in random times, the server is currently running on [vitaes.io](https://vitaes.io/) and can be updated by any of the 2 contributors 

## Notes
In order to enable hot reloading for the webapp while developing in Windows, you need to change the `vitaes-webapp/package.json` start script to `CHOKIDAR_USEPOLLING=true react-scripts start`.


[status_api]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_api_module&metric=alert_status
[status_stolas]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_stolas_module&metric=alert_status
[status_logger]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_logger_module&metric=alert_status
[status_renderer]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_renderer_module&metric=alert_status
[status_storage]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_storage_module&metric=alert_status
[status_webapp]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_webapp_module&metric=alert_status
[status_api_coverage]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_api_module&metric=coverage
[status_stolas_coverage]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_stolas_module&metric=coverage
[status_logger_coverage]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_logger_module&metric=coverage
[status_renderer_coverage]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_renderer_module&metric=coverage
[status_storage_coverage]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_storage_module&metric=coverage
[status_webapp_coverage]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_webapp_module&metric=coverage
[status_api_maintainability]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_api_module&metric=sqale_rating
[status_stolas_maintainability]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_stolas_module&metric=sqale_rating
[status_logger_maintainability]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_logger_module&metric=sqale_rating
[status_renderer_maintainability]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_renderer_module&metric=sqale_rating
[status_storage_maintainability]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_storage_module&metric=sqale_rating
[status_webapp_maintainability]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_webapp_module&metric=sqale_rating
[status_api_security]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_api_module&metric=security_rating
[status_stolas_security]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_stolas_module&metric=security_rating
[status_logger_security]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_logger_module&metric=security_rating
[status_renderer_security]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_renderer_module&metric=security_rating
[status_storage_security]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_storage_module&metric=security_rating
[status_webapp_security]: https://sonarcloud.io/api/project_badges/measure?project=vitaes_webapp_module&metric=security_rating