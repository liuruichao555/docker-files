### 启动docker
 <pre><code>. setenv.sh</code></pre>

 <pre><code>docker-compose up -d</code></pre>
 
### chaincode部署、调用、查询
 <pre><code>docker exec -it dockercompose_vp_1 bash</code></pre>
 
 <pre><code>peer chaincode deploy -p github.com/hyperledger/fabric/examples/chaincode/go/map -c '{"Args": ["init","a", "100"]}'</code></pre>
	*Note: deploy后等待部署完成，20s左右。*
 
<pre><code>CC_ID="1bea54ed60be3a91c700ce69349a2a432ff425b73290f09a9c9b116f5c4a95d379494fcf608752e6589f616afa93543f560220222e24850b64e9dcc009ab1119"</code></pre>
 
 <pre><code>peer chaincode invoke -u jim -n ${CC_ID} -c '{"Args": ["put", "name","liuruichao"]}'</code></pre>
 
 <pre><code>peer chaincode query -u jim -n ${CC_ID} -c '{"Args": ["keys"]}'</code></pre>
 
 <pre><code>peer chaincode query -u jim -n ${CC_ID} -c '{"Args": ["get", "name"]}'</code></pre>

### 停止docker
 <pre><code>docker-compose down</code></pre>


