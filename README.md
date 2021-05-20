

# Overview

A small library that will help you to parse/fetch a text from a source (for example, PDF file). 

There is the Apache Tika library under the hood so all file formats that they are supported you can process with the library

# How to use it

## 1. Get the latest dependency
[![Maven Central](
    https://maven-badges.herokuapp.com/maven-central/com.github.bogdanovmn.txtparser/text-parser/badge.svg
)]( https://maven-badges.herokuapp.com/maven-central/com.github.bogdanovmn.txtparser/text-parser)
```xml
<dependency>
    <groupId>com.github.bogdanovmn.txtparser</groupId>
    <artifactId>text-parser</artifactId>
    <version>...</version>
</dependency>
```

## 2. Pass an InputStream or a File and get a text content of that
```java
DocumentContent pdfContent = DocumentContent.fromInputStream(
	pdfInputSrteam
);

assertTrue(
	pdfContent.text()
		.contains("this string is inside the pdf content")
);
```

## 3. Also you can get a meta-data of a source
```java

DocumentContent doc = DocumentContent.fromFile(docFile);

assertEquals("Jens Rehsack", doc.author());

assertEquals("Cross Compiling For Perl Hackers", doc.title());

assertEquals("application/pdf", doc.contentType());
```