docker run --network="bridge" --rm -i peterevans/vegeta sh -c \
"echo 'GET http://node.local:3000' | vegeta attack -rate=10 -duration=30s | tee node_results.bin | vegeta report"

docker run --network="bridge" --rm -i peterevans/vegeta sh -c "ping -t node.local"

docker run --network="graalvm-nodejs_cloud" --rm -i peterevans/vegeta sh -c \
"echo 'GET http://node.local:3000' | vegeta attack -rate=10 -duration=30s | tee node_results.bin | vegeta report"