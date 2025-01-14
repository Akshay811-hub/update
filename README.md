# Liquibase Update Action
Official GitHub Action to run Liquibase Update in your GitHub Action Workflow. For more information on how update works visit the [Official Liquibase Documentation](https://docs.liquibase.com/commands/home.html).
## Update
Deploy any changes in the changelog file that have not been deployed
## Usage
```yaml
steps:
- uses: actions/checkout@v3
- uses: liquibase-github-actions/update@v4.23.1
  with:
    # The root changelog
    # string
    # Required
    changelogFile: ""

    # The JDBC database connection URL
    # string
    # Required
    url: ""

    # Fully-qualified class which specifies a ChangeExecListener
    # string
    # Optional
    changeExecListenerClass: ""

    # Path to a properties file for the ChangeExecListenerClass
    # string
    # Optional
    changeExecListenerPropertiesFile: ""

    # Changeset contexts to match
    # string
    # Optional
    contextFilter: ""

    # The default catalog name to use for the database connection
    # string
    # Optional
    defaultCatalogName: ""

    # The default schema name to use for the database connection
    # string
    # Optional
    defaultSchemaName: ""

    # The JDBC driver class
    # string
    # Optional
    driver: ""

    # The JDBC driver properties file
    # string
    # Optional
    driverPropertiesFile: ""

    # Changeset labels to match
    # string
    # Optional
    labelFilter: ""

    # Password to use to connect to the database
    # string
    # Optional
    password: ""

    # If set to true and any changeset in a deployment fails, then the update operation stops, and liquibase attempts to rollback all changesets just deployed. A changeset marked "fail-on-error=false" does not trigger as an error, therefore rollback-on-error will not occur. Additionally, if a changeset is not auto-rollback compliant or does not have a rollback script, then no rollback-on-error will occur for any changeset.
    # bool
    # Optional
    rollbackOnError: ""

    # Type of update results summary to show.  Values can be "off", "summary", or "verbose".
    # string
    # Optional
    showSummary: ""

    # Username to use to connect to the database
    # string
    # Optional
    username: ""

```

### Secrets
It is a good practice to protect your database credentials with [GitHub Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

## Optional Liquibase Global Inputs
The liquibase update action accepts all valid liquibase global options as optional parameters. A full list is available in the official [Liquibase Documentation](https://docs.liquibase.com/parameters/command-parameters.html).

### Example
```yaml
steps:
  - uses: actions/checkout@v3
  - uses: liquibase-github-actions/update@v4.23.1
    with:
      changelogFile: ""
      url: ""
      headless: true
      licenseKey: ${{ secrets.LIQUIBASE_LICENSE_KEY }}
      logLevel: INFO
```

## Feedback and Issues
This action is automatically generated. Please submit all feedback and issues with the [generator repository](https://github.com/liquibase/github-action-generator/issues).
