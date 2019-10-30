# Wordcount



```
gsutil ls gs://micro-starter-kit/dataflow/wordcount/
gsutil cp shakespeare.txt  gs://micro-starter-kit/dataflow/wordcount/input/
gsutil cp gs://micro-starter-kit/dataflow/wordcount/input/shakespeare.txt  .
```


```bash
# setup
go mod init github.com/xmlking/wordcount
# build
go build
# run
./wordcount --input shakespeare.txt --output counts



export GOOGLE_APPLICATION_CREDENTIALS="/Users/schintha/Developer/Apps/micro-starter-kit.json"


./wordcount --input gs://micro-starter-kit/dataflow/wordcount/input/shakespeare.txt \
            --output gs://micro-starter-kit/dataflow/wordcount/output/counts \
            --runner dataflow \
            --job_name wordcount1 \
            --project micro-starter-kit \
            --region us-west1 \
            --subnetwork my-subnetwork \
            --temp_location gs://micro-starter-kit/dataflow/wordcount/tmp/ \
            --staging_location gs://micro-starter-kit/dataflow/wordcount/binaries/ \
            --worker_harness_container_image=apachebeam/go_sdk:latest

./wordcount --input gs://micro-starter-kit/dataflow/wordcount/input/shakespeare.txt \
            --output gs://micro-starter-kit/dataflow/wordcount/output/counts \
            --runner dataflow \
            --job_name wordcount1 \
            --project micro-starter-kit \
            --temp_location gs://micro-starter-kit/dataflow/wordcount/tmp/ \
            --staging_location gs://micro-starter-kit/dataflow/wordcount/binaries/ \
            --worker_harness_container_image=apachebeam/go_sdk:latest
```


