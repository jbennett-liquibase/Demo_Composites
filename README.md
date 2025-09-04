<p align="left">
  <img src="img/liquibase.png" alt="Liquibase Logo" title="Liquibase Logo" width="324" height="72">
</p>

# Liquibase Pro Composite Actions

This repository contains composite actions to use in Liquibase Pro demonstrations. If a version or edition needs to be updated, it can be done from a central location.

# ✔️ To Use Composites
Add these composite actions to your GitHub configuration files.
```yaml
- name: Setup AWS
    uses: jbennett-liquibase/Demo_Composites/actions/setup-aws@v1
    with:
    aws-role: ${{ secrets.AWS_ROLE }}

- name: Setup Liquibase
    uses: jbennett-liquibase/Demo_Composites/actions/setup-liquibase@v1

- name: Running Liquibase
    run: liquibase flow --flow-file=liquibase.flowfile.yaml
```

Note: The setup-liquibase composite uses default values for version (4.33.0) and edition (pro). You can override them using "with:" if needed:
```yaml
- name: Setup Liquibase (override version)
  uses: jbennett-liquibase/Demo_Composites/actions/setup-liquibase@v1
  with:
    version: "5.0.0"
```

# 🛠️ To Update Composites
1. Make changes as required
1. Update repository with changes
    ```
    git add actions/setup-liquibase/action.yml
    git commit -m "Update Liquibase composite defaults or version"
    git push origin main
    ```
3. Publish and use a new version
    ```
    git tag v1.1
    git push origin v1.1
    ```

# ☎️ Contact Liquibase
Liquibase sales: https://www.liquibase.com/contact-us<br>
Liquibase support: https://support.liquibase.com