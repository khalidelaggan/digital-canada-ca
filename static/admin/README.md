
## Netlify Meta fields and page form structure references

### [/blog] - [Blog page Netlify](https://digital.canada.ca/admin/#/collections/blog/new)



```
- name: "blog"
    label: "(EN) Blog Post."
    folder: "content/en/blog/posts"
    create: true
    fields:
      - {label: "Layout", name: "layout", widget: "hidden", default: "blog"}
      - {label: "Title / Titre", name: "title", widget: "string"}
      - {label: "Description / Description", name: "description", widget: "string"}
      - {label: "Author, Title / Auteur, Titre", name: "author", widget: "string"}
      - {label: "Publish Date / Date de publication", name: "date", widget: "datetime"}
      - {label: "Banner Image / Image de la bannière", hint: "Max. 1MB", name: "image", widget: "image"}
      - {label: "Image Alt-text / Texte alternatif de l'image", name: "image-alt"}
      - {label: "Blog ID / Identification de blogue", hint: "Use the same ID for both languages / Utilisez la même identification dans les deux langues", name: "translationKey", widget: "string"}
      - {label: "Body / Corps", name: "body", widget: "markdown"}
      - {label: "Thumbnail", name: "thumb", widget: "hidden", default: "" }
      - {label: "Processed", name: "processed", widget: "hidden", default: "" }
```


> Please note that fileds aren't by default set to be required at the time this docs is written however, if one of these entries are missing it makes the page vulnerable to errors and potentially break the CMS.

|  Field         |Description               |Note                         |
|----------------|-------------------------------|-----------------------------|
|`title`           |blog title                 |required                  |
|`description`     |Description           |required            |
|`author`          |Blog Author| required|
|`date`    |Blog publish date            |required            |
|`image`   |an image upload widget            |required           |
|`translationKey`         |Blog ID  |page title split by hyphen(all lowercase), use the same ID for both languages|
|`body`            |Blog Body Content|Blog body|



#### Blog's Hidden Fields 


|  Field         |Description               |Note                         |
|----------------|-------------------------------|-----------------------------|
|`layout`           |'blog title'              |'mandatory'                  |
|`thumb`     |[/util/processBlogImages.js]|'automatically Generated'|
|`processed`          |timestamp by [/util/processBlogImages.js]|'automatically Generated'|


### [/work-with-us/] - [Team page Netlify](https://digital.canada.ca/admin/#/collections/join-our-team/new)

```
- name: "work-with-us"
    label: "(EN) Job Postings"
    folder: "content/en/work-with-us/positions"
    create: true
    fields:
      - { label: "Layout", name: "layout", widget: "hidden", default: "job-posting" }
      - { label: "Type", name: "type", widget: "hidden", default: "section" }
      - { label: "Title / Titre", name: "title", widget: "string" }
      - { label: "Description / Description", name: "description", widget: "string"}
      - { label: "Archived / Archivé", name: "archived", widget: "boolean", default: false}
      - { label: "Job Id", name: "leverId", widget: "string"}
      - { label: "Posting ID / Identification de l’affichage", hint: "Use the same ID for both languages / Utilisez la même identification dans les deux langues", name: "translationKey", widget: "string"}
      - { label: "Body / Corps", name: "body", widget: "markdown"}
```
### [/products/] - [Product page Netlify](https://digital.canada.ca/admin/#/collections/products/new)


```
- name: "products"
    label: "(EN) Products"
    folder: "content/en/products/products"
    create: true
    fields:
      - { label: "Title / Titre", name: "title", widget: "string", required: true }
      - { label: "Product ID / Key", name: "translationKey", hint: "Use the same ID for both languages / Utilisez la même identification dans les deux langues", widget: "string", required: true }
      - { label: "Description / Description", name: "description", widget: "text" }
      - { label: "Link to Product / Lien vers le produit", name: "product-url", widget: "string", required: false}
      - { label: "Phase / Phase", name: "phase", widget: "select", options: ["discovery / découverte", "alpha / alpha", "beta / bêta", "live / en ligne"], required: true}
      - label: "Contact"
        name: "contact"
        widget: "list"
        fields:
          - { label: "Contact Name", name: "name", widget: "string", required: true }
          - { label: "Email / Courriel", name: "email", widget: "string" }
      - label: "Partner(s) / Le(s) partenaire(s)"
        name: "partners"
        widget: "list"
        fields:
          - { label: "Partner Name / Nom du partenaire", name: "name", widget: "string", required: true }
          - { label: "Partner Link / Lien vers le site du partenaire", name: "url", widget: "string" }
      - { label: "Status / État", name: "status", widget: "select", options: ["in-flight", "past"], required: true}
      - label: "Links / Liens"
        name: "links"
        widget: "list"
        required: false
        fields:
          - { label: "Name / Text - Nom / Texte", name: "name", widget: "string"}
          - { label: "URL / Lien URL", name: "url", widget: "string"}
```

### [/meet-the-team/] - [Job Posting Netlify](https://digital.canada.ca/admin/#/collections/datafiles/entries/team)


```
  - label: "Team"
        name: "team"
        file: "data/team.yml"
        fields:
          - label: exec
            name: exec
            widget: list
            fields:
              - {label: name, name: name, widget: string}
              - label: title
                name: title
                widget: object
                fields:
                  - {label: en, name: en, widget: string}
                  - {label: fr, name: fr, widget: string}
              - {label: image-name, name: image-name, widget: image}
              - {label: twitter, hint: "Username Only", name: twitter, widget: string}
              - {label: linkedin, hint: "Username Only", name: linkedin, widget: string}
              - {label: email, name: email, widget: string}
              - {label: github, hint: "Username Only", name: github, widget: string}
              - {label: "Archived / Archivé", name: "archived", widget: "boolean", default: false}
              - {label: "Processed / Traité", name: "processed", widget: "hidden", default: "" }
```

### [/meet-the-team/] - [Team page Netlify](https://digital.canada.ca/admin/#/collections/datafiles/entries/team)

       
```
          - label: team
            name: team
            widget: list
            fields:
              - {label: name, name: name, widget: string}
              - label: title
                name: title
                widget: object
                fields:
                  - {label: en, name: en, widget: string}
                  - {label: fr, name: fr, widget: string}
              - {label: image-name, name: image-name, widget: image}
              - {label: twitter, hint: "Username Only", name: twitter, widget: string}
              - {label: linkedin, hint: "Username Only", name: linkedin, widget: string}
              - {label: email, name: email, widget: string}
              - {label: github, hint: "Username Only", name: github, widget: string}
              - {label: "Archived / Archivé", name: "archived", widget: "boolean", default: false}
              - {label: "Processed / Traité", name: "processed", widget: "hidden", default: "" }
```

