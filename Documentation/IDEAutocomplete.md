#### Intro
You can optionally activate a code generator to create fake abstract classes for your IDE
autocomplete.
This means that when coding you can instantly know what are the attributes present in your model
and the type of data they return.

#### Install

In your config_dev.yml, add this line at the begining:

```yml
imports:
    - { resource: '@SidusEAVModelBundle/Resources/config/annotation_generator.yml' }
```

Create a folder writable by your web server : /app/annotations

Clear your cache and load a page.

The fake classes should be generated in /app/annotations/Sidus/EAV

Theses classes should __NEVER__ be used for real code, only for annotations as they are not valid
PHP classes, they are only generated in your dev environement and you should not version them.

Add to your .gitignore:
```
/app/annotations/*
```

#### Usage:

Use the __@var__ annotation : ```/** @var \Sidus\EAV\FamilyCode $var */```

![Autocomplete Example](assets/autocomplete_example.png)

Note that it will also autocomplete methods presents in the data class you provided for the
family.
