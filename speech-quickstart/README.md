```
gcloud auth activate-service-account --key-file=ivikramtiwari-service-account.json
gcloud auth print-access-token

curl -s -k -H "Content-Type: application/json" \
   -H "Authorization: Bearer token" \
   https://speech.googleapis.com/v1beta1/speech:syncrecognize \
   -d @sync-request.json


#result:

{
  "results": [
    {
      "alternatives": [
        {
          "transcript": "how old is the Brooklyn Bridge",
          "confidence": 0.98267895
        }
      ]
    }
  ]
}
```
