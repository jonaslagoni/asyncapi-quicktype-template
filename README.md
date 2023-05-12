# ARCHIVED: I am working on a much better alternative to this called [Modelina](https://github.com/asyncapi/modelina), and therefore have no reason to keep this library maintained. Happy to help out with any inqueries for type generation over there: https://github.com/asyncapi/modelina

# Template to generate type files for the AsyncAPI Generator

This template generates types based on the desired language specified with the `quicktypeLanguage` parameter. This template generates all the defined message payloads. To fully use this template it is expected to be generated into a project already setup.

Currently this template supports all the Quicktype languages, `C++`,  `C#`,  `crystal`,  `dart`,  `elm`,  `golang`,  `haskell`,  `java`,  `json-schema`,  `javascript`,  `javascript-prop-types`,  `kotlin`,  `pike`,  `python`,  `rust`,  `ruby`,  `swift` and `typescript`.

This template is ONLY a wrapper to the underlying [jonaslagoni/asyncapi-quicktype-filter](https://github.com/jonaslagoni/asyncapi-quicktype-filter). All functionality are located there and is where it interact with the [Quicktype](https://quicktype.io/) libraries.

## Usage

```
ag asyncapi.yaml @lagoni/asyncapi-quicktype-template -o output --param "quick
typeLanguage=java"
```

## Supported parameters

|Name|Description|Required|Allowed values|Example|
|---|---|---|---|---|
|quicktypeLanguage|Define which language types should be generated for.|Yes| `cplusplus`,  `csharp`,  `crystal`,  `dart`,  `elm`,  `golang`,  `haskell`,  `java`,  `jsonschema`,  `javascript`,  `javascriptproptypes`,  `kotlin`,  `pike`,  `python`,  `rust`,  `ruby`,  `swift`,  `typescript`|`"quicktypeLanguage=csharp"`|
|renderOptions|Object to parse on to quicktype when rendering the files.|No|*Object*|`'renderOptions={"package":"testing.io.test"}'`|
|subTargetDir|Filepath relative to the output folder to place the files.|No|*String*|`"subTargetDir=src/test"`|


## Special descriptions for languages
Below is a description on how to use the generated files, I have only tested Java and C#. All the render parameters can be found in the code for each language under the [Quicktype library](https://github.com/quicktype/quicktype/blob/master/src/quicktype-core/language/), I didnt find any actual documentation for this, so you have to find it the hard way.

### Java
Java requires the `jackson` library to compile.

Its render parameters can be found here the actual implementation of [Quicktype](https://github.com/quicktype/quicktype/blob/e6cc44fdfcb75c3f3ed3e12f69f15a0c863a1a05/src/quicktype-core/language/Java.ts#L29).

### C#
C# requires the `Newtonsoft` library to compile.

Its render parameters can be found here the actual implementation of [Quicktype](https://github.com/quicktype/quicktype/blob/e6cc44fdfcb75c3f3ed3e12f69f15a0c863a1a05/src/quicktype-core/language/CSharp.ts#L115).

