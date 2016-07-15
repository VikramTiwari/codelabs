- Create a Maven project
```
$  mvn archetype:generate \
     -DarchetypeArtifactId=google-cloud-dataflow-java-archetypes-examples \
     -DarchetypeGroupId=com.google.cloud.dataflow \
     -DarchetypeVersion=1.6.0 \
     -DgroupId=com.example \
     -DartifactId=first-dataflow \
     -Dversion="[1.0.0,2.0.0]" \
     -DinteractiveMode=false
```

- Run the task

$ mvn compile exec:java \
      -Dexec.mainClass=com.example.WordCount \
      -Dexec.args="--project=ivikramtiwari \
      --stagingLocation=gs://codelab-cloud-dataflow/staging/ \
      --output=gs://codelab-cloud-dataflow/output \
      --runner=BlockingDataflowPipelineRunner"
