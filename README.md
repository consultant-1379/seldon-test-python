
 MyModel.py : example template for runtime model
 requirements.txt : dependencies
 .s2i/environment : add required parameters here

You can also add a setup.py rather than a requirements.txt

How to wrap:
s2i build /root/git/seldon-test-python seldonio/seldon-core-s2i-python3 seldon_python_reference:v1

How to run as standalone container (testing only!!!):
docker run -p 5000:5000 seldon_python_reference:v1

How to interact:
curl -X POST -H "Content-Type: multipart/form-data" --form "json={<PAYLOAD>}" http://localhost:5000/predict

Sample payload:
{"data" : {"ndarray": [1,2,3], "names": ["f1", "f2"]}}


Custom metrics:
test_custom_counter
test_custom_gauge
test_custom_timer
