# The BackBee documentation

## How to contribute ?

The documentation is written in markdown and we use mkdocs to generate the website.
In order to contribute, you need to install python, python-yaml and mkdocs.

Then, use this command:

```bash
$ mkdocs serve
```

You will have the documentation website available in your own computer.

### Register a new page

You need to create the new ``<page>.md`` file and then to register it into ``mkdocs.yml`` configuration file,
in ``pages`` section.

For instance:

```yaml
# mkdocs.yml
pages:
    - Introduction: 'index.md'
    - Developper documentation:
        - 'Requirements': 'developper-documentation/requirements.md'
        - 'Architecture': 'developper-documentation/architecture.md'
        - 'Configuration': 'developper-documentation/configuration.md'
        - 'Project Architecture': 'developper-documentation/project_architecture.md'
        - **'New page': 'new_page.md'**
    - 'Cookbooks':
        - 'Create new commands': 'developper-documentation/cookbooks/create_new_commands.md'
        - 'Customize error pages': 'developper-documentation/cookbooks/customize_error_pages.md'
        - 'Use Swift Mailer in BackBee': 'developper-documentation/cookbooks/use_swift_mailer_in_backbee.md'
        - 'Create bundle administration': 'developper-documentation/cookbooks/create_bundle_administration.md'
        - 'Layout creation using LayoutBuilderBundle': 'developper-documentation/cookbooks/layout_creation.md'
    - 'Components':
        - 'ClassContent': 'developper-documentation/components/classcontent.md'
        - 'Config': 'developper-documentation/components/config.md'
        - 'Event Listener': 'developper-documentation/components/event_listener.md'
        - 'Routing': 'developper-documentation/components/routing.md'
        - 'Security': 'developper-documentation/components/security.md'
        - 'Translation': 'developper-documentation/components/translation.md'
        - 'Nested Node': 'developper-documentation/components/nested_node.md'
```

**Mkdocs** can manage only 1 level of subpage, this configuration:

```yaml
pages:
    - 'foo': 'foo.md'
        - 'bar': 'foo/bar.md'
            - 'baz': 'baz.md'
```

will result to an error, and the website won't be generated.