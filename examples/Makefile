get-python:
	../kubeless function create get-python --trigger-http --runtime python27 --handler helloget.foo --from-file python/helloget.py
	echo "curl localhost:8080/api/v1/proxy/namespaces/default/services/get-python/"

get-nodejs:
	../kubeless function create get-nodejs --trigger-http --runtime nodejs6.10 --handler helloget.foo --from-file nodejs/helloget.js
	echo "curl localhost:8080/api/v1/proxy/namespaces/default/services/get-nodejs/"

get: get-python get-nodejs

post-python:
	../kubeless function create post-python --trigger-http --runtime python27 --handler hellowithdata.handler --from-file python/hellowithdata.py
	echo "curl --data '{\"hello\":\"world\"}' localhost:8080/api/v1/proxy/namespaces/default/services/post-python/ --header "Content-Type:application/json""

post-nodejs:
	../kubeless function create post-nodejs --trigger-http --runtime nodejs6.10 --handler hellowithdata.handler --from-file nodejs/hellowithdata.js
	echo "curl --data '{\"hello\":\"world\"}' localhost:8080/api/v1/proxy/namespaces/default/services/post-nodejs/ --header "Content-Type:application/json""

post: post-python post-nodejs

pubsub:
	../kubeless function create pubsub --trigger-topic s3 --runtime python27 --handler pubsub.handler --from-file python/pubsub.py

topic:
	../kubeless function publish --topic demo --data "s3"
