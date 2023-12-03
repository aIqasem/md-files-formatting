# Creating md tables from spreadsheets

<BR>

> ### About md tables

- ___Basic table___
  ```
  | header 1 | header 2 | header 3 |
  | -------- | -------- | -------- |
  | data     | data     | data     | 
  ```
  | header 1 | header 2 | header 3 |
  | -------- | -------- | -------- |
  | data     | data     | data     | 

  - Indentends of | is not necessary .. but is pretty being indentended
  - Default align: Left

   <BR>

- ___To center the content of a column use___ `| :--: |` ___instead of___ `| -- |`

  ```
  | Centered header 1 | header 2 | header 3 |
  | :--: | -- | -- |
  | data | data | data |
  ```
  | Centered header 1 | header 2 | header 3 |
  | :--: | -- | -- |
  | data | data | data |

<BR>

- ___Similarly .. to align text to the right use___ `| --: |`
  
   ```
    | right header 1 | header 2 | header 3 |
    | --: | -- | -- |
    | data | data | data |
    ```
    | right header 1 | header 2 | header 3 |
    | --: | -- | -- |
    | data | data | data |

  ---

<BR>
<BR>

> ### Simple function for creating md tables from coppied spreadsheet cells

  - This function takes the last coppied item from the clipboard (spreadsheet cells) and returns in md table format.
  - It's output is copied to the clipboard for quick pasting at an md file.
  - For table being nice-looking .. Centered the columns of numbers and checkboxes.
  - Checkboxes .. when coppied from a spreadsheet cell .. it's coppied as `TRUE` or `FALSE`. Try it.

  ```python
  import pyperclip  
  from dateutil import parser


  def is_valid_date(date_string):
    try:
        parser.parse(date_string)
        return True
    except ValueError:
        return False

  def is_numeric(s):
      try:
          num = float(s)
          return isinstance(num, (int, float))
      except ValueError:
          return False
  
  def code(content):
      rows = content.split("\n")
  
      # edit header and create initial 2nd row
      header = ["_" + cell.strip() + "_" for cell in rows[0].split("\t")]
      div = " -- |"
      row2 = f"| -- |{div * (len(header) - 1)}"
  
      # split each row to create each row cells and create a list of the rest rows
      table_rows = ["| " + ' | '.join(row.split('\t')).strip() + " |" for row in rows[1:]]
      
      # get indexes of cells of numbers (got from the 3rd row .. the first one containing data)
      cells = table_rows[2].strip().split("|")[1:-1]
      numbers = []
      for i in range(len(cells)):
          if is_numeric(cells[i]) or cells[i].strip() == "TRUE" or cells[i].strip() == "FALSE" or is_valid_date(cells[i]):
              numbers.append(i)
  
      # for the 2nd row .. edit the header (the "| -- |") of the cells of numbers to center the column .. set it to "| :--: |"
      for i in range(len(numbers)):
          shift = i * 2
          row2 = row2[:numbers[i]*5+shift] + "| :--: |" + row2[(numbers[i]+1)*5+shift + 1:]
  
      # add header and 2nd row at indexes 0 and 1
      table_rows.insert(0, f"| {' | '.join(header)} |")
      table_rows.insert(1, row2)
      
      # get the output as a string to copy to the clipboard
      # replacing the TRUE and FALSE with centered checkboxes (actually .. emoje)
      output = "\n".join(table_rows)
      output = output.replace('| TRUE |',  '| ☑️ |')
      output = output.replace('| FALSE |', '| 🔘 |')
      
      # copy the output
      pyperclip.copy(output)
      return output
  
      
  print(f"\n coppied md table:'\n{code(pyperclip.paste())}\n")
  ```

<BR>

  - ___Running___ :
    - coppied the content of _[this](https://docs.google.com/spreadsheets/d/1xeRlWnW6J5GJUykwMW46cCH8WUgqMTD8QQzBqwO3C1c/edit#gid=0)_ spreadsheet. ( Just select the cells + Ctrl+C 👀 )
    - run the function
    - Output: (output is coppied)<BR>
  ```
    coppied md table:
  | _Checked_ | _Subject_ | _mark_ | _Full mark_ | _Percentage_ |
  | :--: | -- | :--: | :--: | :--: |
  | ☑️ | Computer Vesion | 16.8 | 20 | 84.00% |
  | ☑️ | Network | 30 | 30 | 100.00% |
  | 🔘 | Computer Arch | 0 | 0 | 0 |
  | 🔘 | Natural Language Processing | 0 | 0 | 0 |
  | ☑️ | Machine Learning | 19 | 20 | 95.00% |
  ```
  
<BR>

   - ___When pasted at an md file___ :
     
  | _Checked_ | _Subject_ | _mark_ | _Full mark_ | _Percentage_ |
  | :--: | -- | :--: | :--: | :--: |
  | ☑️ | Computer Vesion | 16.8 | 20 | 84.00% |
  | ☑️ | Network | 30 | 30 | 100.00% |
  | 🔘 | Computer Arch | 0 | 0 | 0 |
  | 🔘 | Natural Language Processing | 0 | 0 | 0 |
  | ☑️ | Machine Learning | 19 | 20 | 95.00% |

---
