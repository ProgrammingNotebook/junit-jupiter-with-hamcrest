# junit-jupiter-with-hamcrest

Junit Jupiter = Junit Jupiter API + Junit Jupiter Engine

## Maven Surefire Plugin Configuration

```xml
<!-- Maven Surefire Plugin -->
<plugin>
    <artifactId>maven-surefire-plugin</artifactId>
    <version>${maven-surefire-plugin.version}</version>
    <configuration>
        <groups>fast</groups>
        <excludedGroups>slow</excludedGroups>
        <properties>
            <configurationParameters>
                junit.jupiter.conditions.deactivate=*
            </configurationParameters>
        </properties>
    </configuration>
</plugin>
```

This is used to run only tests marked with @Tag("fast"), no other tests will run.
```xml
<configuration>
    <groups>fast</groups>
</configuration>
```

This is used to disable the tests that are marked with @Test("slow"), other tests will run fine.
```xml
<configuration>
    <excludedGroups>slow</excludedGroups>
</configuration>
```

This will disable the @Disabled condition and will run the unit tests marked @Disabled. Basically deactivated any diabled conditions.
```xml
<configuration>
    <properties>
        <configurationParameters>
            junit.jupiter.conditions.deactivate=*
        </configurationParameters>
    </properties>
</configuration>
```