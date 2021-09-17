# Abbreviation Definitions
| Status | Heading | Unit | Type | Description | Example |
| --- | --- | :---: | :---: | --- | --- |
| \*R | ABBR\_HDNG | | X | Field heading in group | LOCA\_TYPE |
| \*R | ABBR\_CODE | | X | Abbreviation used | TP |
| R | ABBR\_DESC | | X | Description of abbreviation | Trial Pit |
| | ABBR\_LIST | | X | Source of abbreviation | AGS4 | |
| | ABBR\_REM | | X | Remarks | | 
| | FILE\_FSET | | X | Associated file reference (e.g. contract data specification) | FS1 |

###### Group Notes

* <font size='2'>ABBR is required in all AGS4 data files and describes all abbreviations used in headings defined by the PA data type (Rule 16).</font></li>
* <font size='2' >The AGS Format website (www.agsdataformat.com) lists the standard abbreviations.</font></li>
* <font size='2' >Additional abbreviations, used in any heading in the file, must be defined in this group.</font></li>
* <font size='2' >ABBR_LIST details the list from which the ABBR_CODE originates. For standard AGS headings this value would be ‘AGS4’ to refer to the AGS website.</font></li>



