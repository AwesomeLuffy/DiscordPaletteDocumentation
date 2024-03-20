# FileAttachments

> Each processor is a class that extends UnaryFunction so the use will be the same for all of them.


## FileName

This will contain the whole title like `my_image.png`

```mermaid
    flowchart LR
      input1([FileAttachment]) --> processor[[FileAttachments.fileName]] --> output1([String])
```

## Formatted File Name

This will contain only the name of the file like `my_image`

```mermaid
    flowchart LR
      input1([FileAttachment]) --> processor[[FileAttachments.formattedFileName]] --> output1([String])
```

## File Extension

This will contain the extension of the file like `png`

```mermaid
    flowchart LR
      input1([FileAttachment]) --> processor[[FileAttachments.fileExtension]] --> output1([String])
```

