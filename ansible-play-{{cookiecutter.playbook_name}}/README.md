# {{ cookiecutter.project_name }} - Ansible

{{cookiecutter.description}}

## Requirements

Install role requirements with the following command:

    ansible-galaxy install -r roles/requirements.yml --roles-path=roles

## Usage

Before runnning any ansible playbook you should always run with
`--check` flag to see if it makes any changes.

To configure server as well as deploy app, run:

         ansible-playbook -i {{ cookiecutter.inventory }} {{ cookiecutter.playbook_name }}.yml --diff --check

By default `master` tag is used for docker image. To deploy
only docker container with any tag, invoke:

       ansible-playbook -i {{ cookiecutter.inventory }} {{ cookiecutter.playbook_name }}.yml -t docker -e "_docker_tag=<tag_name>" --diff --check


Above commands are with `--check` flag. To apply changes, remove it.

## License
[{{cookiecutter.license}}](LICENSE)

## Authors
[{{cookiecutter.author}}](https://github.com/{{cookiecutter.author_github}})
