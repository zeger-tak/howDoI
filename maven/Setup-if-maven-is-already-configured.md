
## parent project setup
1. Create a new directory and pom.xml for your parent project:
2. Define the parent pom.xml with common configurations, dependencies, and plugin management.
Example:
```xml

<groupId>[insert_groupid]</groupId>
<artifactId>[insert_artifactid]</artifactId>
<packaging>pom</packaging> <!--For parent modules, use packaging type 'pom', no need for jar-->
<version>1.0.0-SNAPSHOT</version>
<description>Parent project for managing modules, common properties, depencencies, etc.</description>
<properties>
<!-- Define common properties for all modules -->
</properties>
<dependencyManagement>
<!-- Define dependencies with versions to be inherited by child modules -->

</dependencyManagement>

		<!-- Do not use <dependencies> here, only in child modules -->

<build>
<pluginManagement>
	<!-- Defines default versions and configurations for plugins.
	Child modules must explicitly declare the plugin in their own <plugins> section to use these settings.
	It does not automatically apply the plugin to all child modules. -->
</pluginManagement>
<plugins>
	<!-- Applies the plugins only to the parent module itself.
    Child modules do not automatically inherit or execute these plugins unless they also declare them in their own <plugins> section -->
</plugins>
</build>
<modules>
<!-- List of child modules -->
</modules>
<profiles>
<profile>
	<id>dev</id>
	<activation>
		<activeByDefault>true</activeByDefault>
	</activation>
</profile>
<profile>
	<id>ci</id>
	<activation>
		<property>
			<name>env.CI</name>
		</property>
	</activation>
</profile>
</profiles>
```
3. Create subdirectories for each module and add their respective pom.xml files.
