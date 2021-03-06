rundeck-yana2-nodes-plugin
==========================

Provides Node Information from Yana2 to Rundeck

Plug-in Installation
------------

Just drop the build (e.g. rundeck-yana2-nodes-plugin-1.1.jar from the project's Downloads section) into ${rdeck.base}/libext (creating the directory, if necessary) and use the Rundeck project setup UI to configure Yana2 resources as the resource model source.

Setting up Yana2
------------

Here's the minimum Yana XML to load through the Yana2 UI to get your first node:

<!-- Sample XML to establish the minimum set of node types to support default usage of the      -->
<!-- Rundeck rundeck-yana2-nodes-plugin (https://github.com/sharadr/rundeck-yana2-nodes-plugin) -->

    <yana>
      <attributes>
        <attribute id="hostname" filter="String"/>
        <attribute id="osArch" filter="String"/>
        <attribute id="osFamily" filter="String"/>
        <attribute id="osName" filter="String"/>
        <attribute id="osVersion" filter="String"/>
        <attribute id="username" filter="String"/>
      </attributes>

      <nodetypes>
        <nodetype id="node">
          <description>Rundeck node (system/server) type</description>
          <image>Node.png</image>
          <nodeAttributes>
            <nodeAttribute id="node.hostname" attribute="hostname" required="true"/>
            <nodeAttribute id="node.osArch" attribute="osArch" required="false"/>
            <nodeAttribute id="node.osFamily" attribute="osFamily" required="false"/>
            <nodeAttribute id="node.osName" attribute="osName" required="false"/>
            <nodeAttribute id="node.osVersion" attribute="osVersion" required="false"/>
            <nodeAttribute id="node.username" attribute="username" required="false"/>
          </nodeAttributes>
        </nodetype>
      </nodetypes>

      <nodes>
        <node id="centos62-rundeck-tomcat" nodetype="node" tags="tag1,tag2,tag3">
          <description>Sample node instance</description>
          <values>
            <attributeValue nodeAttribute="node.hostname">centos62-rundeck-tomcat</attributeValue>
            <attributeValue nodeAttribute="node.osArch">amd64</attributeValue>
            <attributeValue nodeAttribute="node.osFamily">unix</attributeValue>
            <attributeValue nodeAttribute="node.osName">Linux</attributeValue>
            <attributeValue nodeAttribute="node.osVersion">2.6.32-220.el6.x86_64</attributeValue>
            <attributeValue nodeAttribute="node.username">tomcat</attributeValue>
          </values>
        </node>
      </nodes>
    </yana>