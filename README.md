## ElasticSearch RPM Test

This is project is an import of https://github.com/nVisium/django.nV to simulate a python project.

### RPM 
Run the following command to download [ElasticSearch](https://www.elastic.co/guide/en/elasticsearch/reference/6.8/rpm.html) rpm packages before scanning.

```
git clone https://github.com/samq-ghdemo/ElasticSearch-RPM-Python.git && cd ElasticSearch-RPM-Python
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.8.23.rpm
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.8.12.rpm
```
### Mend Scan
Use the following commands to scan with the unified agent
```
curl -LJO https://unified-agent.s3.amazonaws.com/wss-unified-agent.jar
export WS_APIKEY=replace-with-your-api-key
export WS_USERKEY=replace-with-your-user-key
export WS_PRODUCTNAME=$(basename -s .git $(git config --get remote.origin.url))
export WS_PROJECTNAME=$WS_PRODUCTNAME-$(git branch --show-current)
java -jar wss-unified-agent.jar
```
