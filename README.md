# shade-plugin-issue

How to replicate:
```
cd simple-dep
mvn install

cd ../bundle
mvn install
```

The artifact in bundle will contain many dependencies even though `spark-core_2.12` 
is defined as `provided` in the `dependencyManagement` and there should be no other dependencies.

The effective pom for the bundle ssems to be alright as well, but for some reason 
the shade plugin is including the transitive dependencies of `spark-core_2.12`.