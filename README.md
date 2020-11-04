# Jessica's Text to Knowledge Graph Engine

Extracting texts from MP3 audio, JPG images, and text documents. Converting text to Knowledge Graph. Linking the text to the DBpedia entities' URL. Not only the directly mentioned entities but also the entities hidden in the DBpedia, but closely related to the content of the text.

## starting the service

```bash
docker pull gaoyuanliang/jessica_text_to_knowledge_graph:1.0.2

docker run -it \
-v /Users/liangyu/Downloads/:/Users/liangyu/Downloads/ \
-p 7474:7474 \
-p 7687:7687 \
-p 9000:9000 \
-p 8080:8080 \
gaoyuanliang/jessica_text_to_knowledge_graph:1.0.2
```

## the interface

input your data at rest API: http://0.0.0.0:9000/

view your output at neo4j: http://0.0.0.0:7474/ with a Cypher code

```
MATCH p=()-->() RETURN p LIMIT 100
```

## input examples in JSON format

### Text2KnowledgeGraph
```python
{
	"text": "I live in Abu Dhabi but study in Dubai."
}

{
	"text": "I want to work for Apple. Steve Jobs is my idol. I want to work in California. "
}

{
  "text": "I am from Shandong of China, and study at the Heriot-Watt University. I love shopping at Taobao of Alibaba."
}
```

### Cocktail2KnowledgeGraph
```python
{
	"document_path":[
	"/jessica_text.txt",
	"/jessica_voice.mp3",
	"/jessica_etisalat.jpeg",	
	"/jessica_dubai_photo.jpg"]
}

{
	"document_path":[
	"/Users/liangyu/Downloads/jessica_text.txt",
	"/Users/liangyu/Downloads/jessica_voice.mp3",
	"/Users/liangyu/Downloads/jessica_etisalat.jpeg",	
	"/Users/liangyu/Downloads/jessica_dubai_photo.jpg"]
}
```

## outputs 
<table>
  <thead>
    <tr>
      <th>Input</th>
      <th>Output</th>
    </tr>
  </thead>
  <tr>
    <td>      
      <img src="WX20201101-102711@2x.png" height="280">
    </td>
    <td>
<img src="WX20201101-102731@2x.png" height="280">
    </td>
  </tr>
  <tr>
    <td>  
<img src="WX20201101-102800@2x.png" height="280">
    </td>
    <td>
<img src="WX20201101-102829@2x.png" height="280">
    </td>
  </tr>
</table>

## what is inside the engine

<img src="WX20201101-104653@2x.png" height="400">

## contact me

by email gaoyuanliang@outlook.com if you want to know more about my engine, or schedule a live demo by me.

I am open to an internship/part-time job in data science/AI. Next year I will graduate from Heriot-Watt University Dubai, open for a full-time job. 

## Thanks given to 

This engine is heavily based on the RDF knowledge graph database and its SPARQL query language. Links to RDF and SPARQL from 
Heriot-Watt Semantic Web Lab: http://www.macs.hw.ac.uk/SWeL/2019/10/28/sparql-for-beginners/

### RDF
<img src="WX20201101-151322@2x.png" height="100">

###  SPARQL 
<img src="WX20201101-151348@2x.png" height="100">
