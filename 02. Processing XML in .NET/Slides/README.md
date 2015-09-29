<!-- section start -->

<!-- attr: {id: 'title', class: 'slide-title', hasScriptWrapper: true} -->

# Processing XML in .NET
## DOM Parser, Streaming Parser, XPath, LINQ to XML
<div class="signature">
    <p class="signature-course">Databases</p>
    <p class="signature-initiative">Telerik Software Academy</p>
    <a href="http://academy.telerik.com" class="signature-link">http://academy.telerik.com</a>
</div>

<!-- section start -->
<!-- attr: {id: 'table-of-contents', class:'table-of-contents'} -->
# Table of Contents
* [Processing XML documents in .NET](#)
  * [Using the DOM Parser](#)
  * [Using the Streaming Parser](#)
* [Using XPath to Search in XML Documents](#)
* [Using LINQ-To-XML](#)
* [XSL Transformation in .NET](#)

<!-- section start -->
<!-- attr: {id: '', class: 'slide-section', showInPresentation:true, hasScriptWrapper:true } -->
<!-- # The DOM Parser
## Parsing XML Documents as DOM Trees -->

<!-- attr: { hasScriptWrapper:true } -->
# The DOM Parser
* The following XML document is given:

```xml
<?xml version="1.0"?>
<library name=".NET Developer's Library">
  <book>
    <title>Professional C# 4.0 and .NET 4</title>
    <author>Christian Nagel</author>
    <isbn>978-0-470-50225-9</isbn>
  </book>
  <book>
    <title>Silverlight in Action</title>
    <author>Pete Brown</author>
    <isbn>978-1-935182-37-5</isbn>
  </book>
</library>
```

<!-- attr: { hasScriptWrapper:true, showInPresentation:true } -->
<!-- # The DOM Parser -->
* This document is represented in the in the memory as a `DOM tree` in the following way:
<img class="slide-image" src="imgs/dom-parser.png" style="position:initial" />

<!-- attr: { hasScriptWrapper:true } -->
# The DOM Parser – Example
```cs
XmlDocument doc = new XmlDocument();
doc.Load("library.xml");
XmlNode rootNode = doc.DocumentElement;
Console.WriteLine("Root node: {0}", rootNode.Name);
foreach (XmlAttribute atr in rootNode.Attributes)
{
  Console.WriteLine("Attribute: {0}={1}",
    atr.Name, atr.Value);
}
foreach (XmlNode node in rootNode.ChildNodes)
{
  Console.WriteLine("\nBook title = {0}",
    node["title"].InnerText);
  Console.WriteLine("Book author = {0}",
    node["author"].InnerText);
  Console.WriteLine("Book isbn = {0}",
    node["isbn"].InnerText);
}
```

<!-- attr: { showInPresentation:true } -->
<!-- # Parsing XML Document with the DOM Parser -->
## [Demo]()

# Classes to Work with DOM
* The DOM parser provides few important classes:
  * `XmlDocument`
    * Represents the DOM tree
    * Usually contains two elements:
      * Header part (prolog) 
      * The root element of the XML document
  * `XmlNode`
    * Abstract base class for all nodes in a DOM tree

<!-- attr: { showInPresentation:true } -->
<!-- # Classes to Work with DOM -->
* `XmlElement`
  * Represents a XML element
* `XmlAttribute`
  * Represents an attribute of an XML tag (couple name-value)
* `XmlAttributeCollection`
  * List of XML attributes attached to an element
* `XmlNodeList`
  * List of XML DOM nodes

# The XmlNode Class
* The class `System.Xml.XmlNode`:
  * Fundamental for the DOM processing
  * Represents a base node
  * Its inheritor-classes are:
    * `XmlDocument`, `XmlElement`, `XmlAttribute`, `XmlDeclaration`, …
  * Allows navigation in the DOM tree:
    * `ParentNode` – returns the parent node (`null` for the root)

# The XmlNode Class








<!-- section start -->
<!-- attr: {id: '', class: 'slide-section', showInPresentation:true, hasScriptWrapper:true } -->
<!-- # 
##  -->

<!-- section start -->
<!-- attr: {id: '', class: 'slide-section', showInPresentation:true, hasScriptWrapper:true } -->
<!-- # 
##  -->

<!-- section start -->
<!-- attr: {id: '', class: 'slide-section', showInPresentation:true, hasScriptWrapper:true } -->
<!-- # 
##  -->

<!-- section start -->
<!-- attr: {id: '', class: 'slide-section', showInPresentation:true, hasScriptWrapper:true } -->
<!-- # 
##  -->

<!-- section start -->
<!-- attr: {id: 'questions', class: 'slide-section'} -->
# Questions
## Databases
