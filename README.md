# Buto-Plugin-TcpdfVersion_6_4_2

Render PDF from YML data.


## Widget output

```
type: widget
data:
  plugin: tcpdf/version_6_4_2
  method: output
  data:
    PDF_PAGE_FORMAT: A4
    margin:
      left: 15
      top: 15
      right: 10
    print_header: true
    print_footer: true
    author: 'Buto - PluginTcpdfVersion_6_4_2'
    title: 'Title'
    subject: 'Subject'
    keywords: 'Buto, Pdf'
    header_logo: '/plugin/tcpdf/version_6_4_2/img/logo.png'
    header_logo_width: '30'
    header_title: 'PluginTcpdfVersion_6_4_2'
    header_string: 'Buto plugin wrapped around tcpdf.'
    footer_text: 'A Buto solution'
    html: ''
    filename: 'buto_tcpdf_version_6_4_2.pdf'
    data_method_REMOVE_THIS_TO_RUN_DATA_METHOD:
      plugin: 'tcpdf/version_6_4_2'
      method: data_method_example
    clean_up_method_REMOVE_THIS_TO_RUN_CLEAN_UP_METHOD:
      plugin: 'tcpdf/version_6_4_2'
      method: clean_up_method_example
    pages:
      -
        - {method: MoveY, data: {y: 10}}
        -
          method: Image
          data:
            file: '[app_dir]/web/plugin/tcpdf/version_6_4_2/img/logo.png'
            w: 60
            h: 50
        - {method: MoveY, data: {y: 60}}
        - {method: SetTextColor, data: {col1: 255, col2: 0, col3: 0}}
        - {method: SetFont, data: {size: 10, style: 'B'}}
        -
          method: Cell
          data:
            txt: Cell with bold red text.
            w: 60
            h: 5
        -
          method: Cell
          data:
            txt: Cell with bold red text without a border.
            border: 0
            w: 80
            h: 5
        - {method: Ln}
        - {method: SetTextColor, data: {col1: 0, col2: 0, col3: 0}}
        - {method: SetFont, data: {size: 10}}
        -
          method: Cell
          data:
            txt: Cell with black text in a new row by calling Ln.
            w: 120
            h: 5
        - {method: Ln}
        -
          method: MultiCell
          data:
            txt: 'MultiCell'
            w: 40
            h: 30
        -
          method: MultiCell
          data:
            txt: 'MultiCell are normaly in a new row like this.'
            w: 40
            h: 30
        -
          method: MultiCell
          data:
            txt: 'But this MultiCell are right aligned because of x and y_minus params.'
            w: 40
            h: 30
            x: 60
            y_minus: 30
        - {method: MoveY, data: {y: 10}}
        -
          method: Cell
          data:
            txt: This Cell are moved down by calling MoveY before.
            w: 120
            h: 5
        - {method: MoveY, data: {y: 10}}
        -
          method: Cell
          data:
            txt: One could draw a line by the Line method.
            w: 120
            h: 5
        - {method: Line, data: {x1: 10, y1: 150, x2: 100, y2: 150, style: {width: 1}}}
        -
          method: new_page
          _: Add a new page if Y is more than 250.
          data:
            y: 250

```

### I18N

MultiCell and Cell are translated with PluginI18nTranslate_v1.

### New page

Om could use method new_page to add a new page depending on Y.

### Enabled or Disabled
Use this settings to hide element.
```
-
  method: Cell
  settings:
    enabled: false
  data:
    txt: This element is not showing up.
    w: 120
    h: 5
```
```
-
  method: Cell
  settings:
    disabled: true
  data:
    txt: This element is not showing up.
    w: 120
    h: 5
```

### Output

Default output is in browser.
```
        dest: I
```
Download file.
```
        dest: D
        filename: 'pdf_create_test.pdf'
```
Save file.
```
        dest: F
        filename: '[app_dir]/theme/[theme]/page/pdf_create_test.pdf'
```

### PDF_PAGE_FORMAT

Default value.
```
    PDF_PAGE_FORMAT: A4
```
Custom value.
```
    PDF_PAGE_FORMAT:
      - 148
      - 300
```
