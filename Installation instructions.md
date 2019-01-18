Create elastic user

    useradd elastic

Set password for the user

    passwd elastic

Switch user

    su elastic

Download elasticsearch

    wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.5.4.tar.gz

Download Kibana

    wget https://artifacts.elastic.co/downloads/kibana/kibana-6.5.4-linux-x86_64.tar.gz

Unzip files:

    tar -xzf elasticsearch-6.5.4.tar.gz
    tar -xzf kibana-6.5.4-linux-x86_64.tar.gz


Edit elasticsearch-6.5.4/config/elasticsearch.yml and add following lines:

    cluster.name: elastic-training
    network.host: _eth0:ipv4_

Edit kibana-6.5.4-linux-x86_64/config/kibana.yml and add the following:

    server.host: 0.0.0.0
    elasticsearch.url: "http://< host-name >:9200"

Start the elasticsearch server:

    elasticsearch-6.5.4/bin/elasticsearch & 

Start the Kibana server:

    kibana-6.5.4-linux-x86_64/bin/kibana &

Check if Elasticsearch is up and running:

    curl -XGET < host-name >:9200

You should see some JSON output if ES is running.

Point your browser to:

    http://< host-name >:5601
This opens Kibana. Go to ***Dev Tools*** to get started with elastic queries
