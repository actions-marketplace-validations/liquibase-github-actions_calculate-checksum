# Liquibase Calculate Checksum Action
Official GitHub Action to run Liquibase Calculate Checksum in your GitHub Action Workflow. For more information on how calculate checksum works visit the [Official Liquibase Documentation](https://docs.liquibase.com/commands/home.html).
## Calculate Checksum
Calculates and prints a checksum for the changeset
## Usage
```yaml
steps:
- uses: actions/checkout@v3
- uses: liquibase-github-actions/calculate-checksum@v4.17.2
  with:
    # The root changelog file
    # string
    # Required
    changelogFile: ""

    # Changeset ID identifier of form filepath::id::author
    # string
    # Required
    changesetIdentifier: ""

    # The JDBC database connection URL
    # string
    # Required
    url: ""

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

    # The database password
    # string
    # Optional
    password: ""

    # The database username
    # string
    # Optional
    username: ""

```

### Secrets
It is a good practice to protect your database credentials with [GitHub Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

## Optional Liquibase Global Inputs
The liquibase calculate checksum action accepts all valid liquibase global options as optional parameters. A full list is available in the official [Liquibase Documentation](https://docs.liquibase.com/parameters/command-parameters.html).

### Example
```yaml
steps:
  - uses: actions/checkout@v3
  - uses: liquibase-github-actions/calculate-checksum@v4.17.2
    with:
      changelogFile: ""
      changesetIdentifier: ""
      url: ""
      headless: true
      licenseKey: ${{ secrets.LIQUIBASE_LICENSE_KEY }}
      logLevel: INFO
```

## Feedback and Issues
This action is automatically generated. Please submit all feedback and issues with the [generator repository](https://github.com/liquibase/github-action-generator/issues).
