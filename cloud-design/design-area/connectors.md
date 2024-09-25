# Connectors

### Description

A connector is a line that connects two resources in the architecture. It is used to show a relationship between two resources. There are two types of connectors:

* **Visual connectors**: Are used to show a visual relationship between two resources. They are represented by a solid line.

![Visual connector](../../.gitbook/assets/visual-connectors.png)

* **Relationship connectors**: Are used to show a relationship between two resources and can be **depends\_on** or **normal** relationship connectors. They are represented by a solid line with the corresponding text in the middle of the connector: **depends\_on** if it's a **depends\_on** relationship connector or the name of the relationship if it's a **normal** relationship connector, eg **server\_name**.

![Depends\_on connector](../../.gitbook/assets/depends-on-connector.png)

![Relationship connector](../../.gitbook/assets/normal-relantionship-connector.png)

### How to create a connector

To create a **visual** connector, you need to follow these steps:

1. Select a resource by clicking on it and then select the **Add connector** option from the node options.

![Add connectors button](../../.gitbook/assets/add-connectors-button.png)

2. Click the generated connector and drag it over the resource you want to connect it to.
3. Release the connector over the resource you want to connect it to.

To create a **depends\_on** relationship connector, you need to follow these steps:

1. Select a resource by clicking on it and open its cloud configuration by clicking on the **Cloud configuration** button from the node options bar.

![Node cloud configuration button](../../.gitbook/assets/node-cloud-configuration.png)

2. Either scroll to the **Extra attributes** section, expand it and click on the **Depends on** input or using the search bar, search for **Depends on**.

![Node cloud configuration](../../.gitbook/assets/depends-on-id-card.png)

3. Clicking on the **Depends on** input will recommend you resources that you can connect to. You can either click on the resource you want to connect to or type the name of the resource you want to connect to.
4. After selecting an item from the list, a connector will be created between the two resources. It will also have a text in the middle of the connector that says **depends\_on** and the automatically generated Terraform code will have the **depends\_on** attribute added to the resource.

![Depends\_on connector](../../.gitbook/assets/depends-on-connector.png)

To create a **normal** relationship connector, you need to follow these steps (the initial steps are the same as for the **depends\_on** relationship connector):

1. Select a resource by clicking on it and open its cloud configuration by clicking on the **Cloud configuration** button from the node options bar.

![Node cloud configuration button](../../.gitbook/assets/node-cloud-configuration.png)

2. Select an input (eg **Key vault secret id**) or use the search bar to search for an input.
3. Clicking on the input will recommend you resources that you can connect to. You can either click on the resource you want to connect to or type the name of the resource you want to connect to.
4. After selecting an item from the list, a connector will be created between the two resources. It will also have a text in the middle of the connector that refers to the field that connects the two resources (eg **key\_vault\_secret\_id**).

![Relationship connector](../../.gitbook/assets/normal-relantionship-connector.png)

### How to delete a connector

To delete a connector, you need to follow these steps:

1. Select the connector by clicking on it and then press the **Delete** key on your keyboard.
2. Select the connector start or end point and select the **Delete connector** option from the connector options or press the **Delete** key on your keyboard.

![Delete connector button](../../.gitbook/assets/delete-connector.png)

### How to edit a connector

To edit a connector, you need to follow these steps:

1. Select the connector by clicking on it and the connector options bar will appear just under the design area options bar.

![Connector options bar](../../.gitbook/assets/connector-options-bar.png)

2. Select the connector start or end point and the connector options will appear on the right side, just next to the selected point.

![Connector icon options](../../.gitbook/assets/connector-icon-options.png)

### Connector options bar

The connector options bar allows you to visually configure the connector and it has the following options:

* **Fill color**: Allows you to change the connector fill color.

![Connector fill color](../../.gitbook/assets/fill-color.png)

* **Border weight**: Allows you to change the connector border weight.

![Connector border weigth](../../.gitbook/assets/border-weigth.png)

* **Border dash**: Allows you to change the connector border dash.

![Connector border dash](../../.gitbook/assets/border-dash.png)

* **Connector type**: Allows you to change the connector type visually, from a straight line to a curved line.

![Connector type](../../.gitbook/assets/connector-type.png)

* **Connector start shape**: Allows you to change the connector start shape, from nothing, to a circle, square or arrow.

![Connector start shape](../../.gitbook/assets/connector-start-shape.png)

* **Connector end shape**: Allows you to change the connector end shape, from nothing, to a circle, square or arrow.

![Connector end shape](../../.gitbook/assets/connector-end-shape.png)

### Connector options

The connector options allow you to configure the connector and it has the following options:

* **Edit text**: Allows you to edit the connector text.

![Connector edit text](../../.gitbook/assets/edit-text.png)

* **Unlink connector**: Allows you to unlink the connector from the target resource so that it can be moved freely and connected to another resource.

![Unlink connector](../../.gitbook/assets/unlink-connector.png)

* **Delete connector**: Allows you to delete the connector.

![Delete connector](../../.gitbook/assets/delete-connector.png)
