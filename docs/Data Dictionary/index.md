# Data Dictionary

The data dictionary is a structured list of all the data items that may be recorded during geotechnical and geoenvironmental investigations (including testing, construction and monitoring). The data dictionary is maintained by the AGS Data Management Working Group. The data items are those which are required to be reported by the standards and specifications used for carrying out the work; for example BS 5930, BS 1377, BS EN ISO 17892 etc. The data dictionary organises these items into Groups, each Group is for a specific part of the investigation such as the location of an investigation point, the description of excavation of the borehole, a laboratory test or an in situ test.

Each Group contains a list of data Headings which contain the individual data variables and data items (such as data types, units and descriptions).

For a specific project it may be practical to extract a limited set of Groups if many of the other Groups are not needed.

Additions to the data dictionary for the project must be clearly included in the specification and agreed between data providers and receivers at the outset of the project.


## Data Format Schema (Group Hierarchy)

AGS4 Groups are organised in a hierarchy. At the top of the hierarchy is the PROJ Group, with the majority of other Groups below this.

One of the Groups immediately below PROJ is Location Details (LOCA). All of the in situ testing data lies directly below LOCA; for example SPT results in the ISPT Group. LOCA is termed the &#39;parent&#39; Group of ISPT and ISPT is termed a &#39;child&#39; Group of LOCA. The parent group of all the laboratory testing is sample data (SAMP).

![Placeholder](RackMultipart20210916-4-s2bcxc_html_57608dfeb54a0dfe.png) A Group has only one parent defined in the Hierarchy, but there can be many child Groups below each parent. Each child Group is linked to its parent Group by the Key Fields.

The table in section 3.6 defines the Group hierarchy by indicating the parent for each Group. The Key Fields that create the link between these Groups are indicated in the Data Dictionary.

There are ten Groups that are not part of this hierarchy and relate to the data file submission and description. The PROJ, TRAN, ABBR, TYPE, DICT, FILE, UNIT, LBSG, PREM and STND Groups each have a general purpose to describe the content of the data file as follows:

- The PROJ, TRAN, ABBR, TYPE and UNIT Groups shall always be included in an AGS file as they define the project, the submission details and the abbreviations, data types and units used within the data file (see rules 13,14,15,16,17).
- The DICT Group shall be included if any user defined Groups or Headings are present. (Rule 18)
- The STND Group should be used to list the various standards and specifications that define the methods by which the data has been collected.
- The LBSG Group should be used to transfer laboratory test scheduling.
- The PREM Group should be used to give time-related remarks that refer to the project as a whole and not to any specific location or test.
- The FILE Group should be used if any associated files (non-AGS Format files) are included in the submission (Rule 20).


## Heading Status

Each Heading has a defined status as listed below:

| **Status**** Indicator **|** Description **|** Example / Notes** |
| --- | --- | --- |
| \* | KEY All KEY Headings shall be included in the group. The combination of data recorded within the KEY Headings of each group shall be unique. | Rule 10a refers.|
| R | REQUIRED Data under these headings shall not be null. | Rule 10b &amp; Rule 12 refers.The AGS Edition Reference shall be included under the TRAN\_AGS Heading to associate the file to the document that contains the specification of Headings. |
| | OTHERThe presence of these Headings and data under these Headings are dictated by the scope of the project specification. |




## Data Types

The TYPE and UNIT selected for a heading are inter-linked.

The data types for each heading are provided in the Data Dictionary. The types in the data dictionary should be used unless otherwise agreed between data provider and receiver in accordance with a project specification.

| **Type** | **Description** | **Example / Notes** |
| --- | --- | --- |
| ID | Unique Identifier | An ID is a unique identifier used across the project.The ID shall be unique in the parent group but may be repeated in child groups i.e. SAMP (parent) vs ELRG (child), LOCA (parent) vs SAMP (child). |
| PA | Text listed in ABBR Group | Abbreviations listed in ABBR group. Rule 16 refers.The list of standard abbreviations and descriptions are presented on the AGS website and shall not be redefined. Other abbreviations may be defined as required within a project, but shall not match/impersonate existing standard abbreviations e.g. &quot;CP&quot; for &#39;Cable percussion&#39; in LOCA\_TYPE shall not be given a non-standard abbreviation defined as &quot;CH&quot; for &#39;Cable hole&#39;; likewise &quot;SCP&quot; (Static cone penetrometer) shall not be replaced by a non-standard abbreviation of &quot;CPT&quot; (Cone penetration test). Multiple abbreviations can be used in a data VARIABLE. Where this occurs, abbreviations are joined using the concatenation character defined in TRAN\_RCON (a &quot;+&quot; character by default). |
| PT | Text listed in TYPE Group | Abbreviations listed in TYPE group. Rule 17 refers. |
| PU | Text listed in UNIT Group | Abbreviations listed in UNIT group. Rule 15 refers.The list of standard units and descriptions are presented on the AGS website and shall not be redefined.This list is case sensitive. |
| X | Text | Abbreviations used in text data shall be listed in the ABBR group. Rule 16 refers. |
| XN | Text / numeric | There are some measured parameters that are typically numeric but can have a valid result that is text; examples include plastic limit (34 or NP) and depth of water in a borehole (2.34 or dry).Abbreviations used in text data shall be listed in the ABBR group. Rule 16 refers. |
| T | Elapsed Time | e.g. hh:mm:ss |
| DT | Date time in international format | yyyy-mm-ddThh:mm:ss.sssZ(+hh:mm) or yyyy-mm-dd or hh:mm:ss or yyyy This format may be used in full or part based on user requirements |
| MC | British Standard BS1377 : Part 2 reported moisture content | _This data type is included for legacy reasons and not used in AGS 4.1_ |
| _n_DP | Value with required number of decimal places | e.g. 2DP = 2 decimal places = 2.34 |
| _n_SF | Value with required number of significant figures | e.g. 2SF = 2 significant figures = 1.2, 10 |
| _n_SCI | Scientific Notation with required number of decimal places | e.g. 73100 as 2SCI = 7.31E4; 73100 as 1SCI = 7.3E4 |
| U | Value with a variable format | This is used for fields that contain values with differing accuracy; e.g. AGS 4.1 = ELRG\_RVAL (AGS 4.0 = ERES\_RVAL). |
| DMS | Degrees:Minutes:Seconds | e.g. 51:28:52.498 |
| YN | Yes or No | Data in the file will be either a _Y_ or _N_ or _Null_ (Rule 12)e.g. Y |
| RL | Record Link| Rule 11 refers.Text in specified format that refers to one or more records in other Groups by Key headings. |


## Units of Measurement

The units for each heading are provided in the Data Dictionary. The units should be in accordance with the specifications and standards used in the UK. The units in the data dictionary should be used unless otherwise agreed between data provider and receiver in accordance with a project specification.


## Heading Examples

Typical examples are given against most of the data Headings to indicate the type of information that might be expected. They are intended to be representative but might not be mutually compatible.


## Groups and Headings

| **Group Name** | **Contents** | **Notes** | **Parent Group** |
| --- | --- | --- | --- |
| [PROJ](Project Information) | Project Information | Required in all files (Rule 13) | - |
| [ABBR](Abbreviation Definitions) | Abbreviation Definitions | Required in all files (Rule 16) | - |
| [DICT](#DICT) | User Defined Groups and Headings | Required in all files which include user defined groups and/or headings (Rule 18) | - |
| [FILE](#FILE) | Associated Files | Required in file if FILE\_FSET data provided in any group (Rule 19) | - |
| [TRAN](#TRAN) | Data File Transmission Information / Data Status | Required in all files (Rule 14) | - |
| [TYPE](#TYPE) | Definition of Data Types | Required in all files (Rule 17) | - |
| [UNIT](#UNIT) | Definition of Units | Required in all files (Rule 15) | - |
| [AAVT](Aggregate Abrasion Tests) | Aggregate Abrasion Tests | SAMP |
| [ACVT](#ACVT) | Aggregate Crushing Value Tests | SAMP |
| [AELO](#AELO) | Aggregate Elongation Index Tests | SAMP |
| [AFLK](#AFLK) | Aggregate Flakiness Tests | SAMP |
| [AIVT](#AIVT) | Aggregate Impact Value Tests | SAMP |
| [ALOS](#ALOS) | Los Angeles Abrasion Tests | SAMP |
| [APSV](#APSV) | Aggregate Polished Stone Tests | SAMP |
| [ARTW](#ARTW) | Aggregate Determination of the Resistance to Wear (micro-Deval) | SAMP |
| [ASDI](#ASDI) | Slake Durability Index Tests | SAMP |
| [ASNS](#ASNS) | Aggregate Soundness Tests | SAMP |
| [AWAD](#AWAD) | Aggregate Water Absorption Tests | SAMP |
| [BKFL](#BKFL) | Exploratory Hole Backfill Details | LOCA |
| [CBRG](#CBRG) | California Bearing Ratio Tests – General | SAMP |
| [CBRT](#CBRT) | California Bearing Ratio Tests - Data | CBRG |
| [CDIA](#CDIA) | Casing Diameter by Depth | LOCA |
| [CHIS](#CHIS) | Chiselling Details | LOCA |
| [CHOC](#CHOC) | Chain of Custody Information | SAMP |
| [CMPG](#CMPG) | Compaction Tests - General | SAMP |
| [CMPT](#CMPT) | Compaction Tests - Data | CMPG |
| [CONG](#CONG) | Consolidation Tests - General | SAMP |
| [CONS](#CONS) | Consolidation Tests - Data | CONG |
| [CORE](#CORE) | Coring Information | LOCA |
| [CTRC](#CTRC) | Cyclic Triaxial Tests - Consolidation | CTRG |
| [CTRD](#CTRD) | Cyclic Triaxial Tests - Data | CTRP |
| [CTRG](#CTRG) | Cyclic Triaxial Test - General | SAMP |
| [CTRP](#CTRP) | Cyclic Triaxial Test - Derived Parameters | CTRC |
| [CTRS](#CTRS) | Cyclic Triaxial Tests - Saturation | CTRG |
| [DCPG](#DCPG) | Dynamic Cone Penetrometer Tests – General | LOCA |
| [DCPT](#DCPT) | Dynamic Cone Penetrometer Tests – Data | DCPG |
| [DETL](#DETL) | Stratum Detail Descriptions | LOCA |
| [DISC](#DISC) | Discontinuity Data | LOCA |
| [DLOG](#DLOG) | Driller Geological Description | LOCA |
| [DOBS](#DOBS) | Drilling/Advancement Observations &amp; Parameters | LOCA |
| [DPRG](#DPRG) | Dynamic Probe Tests - General | LOCA |
| [DPRB](#DPRB) | Dynamic Probe Tests - Data | DPRG |
| [DREM](#DREM) | Depth Related Remarks | LOCA |
| [ECTN](#ECTN) | Sample Container Details | SAMP |
| [ELRG](#ELRG) | Environmental Laboratory Reporting | SAMP |
| [<del>ERE</del>](#ERES) | <del>Environmental Contaminant Testing</del> | This group has been deprecated, see ELRG | <del>SAMP</del> |
| [ESCG](#ESCG) | Effective Stress Consolidation Tests – General | SAMP |
| [ESCT](#ESCT) | Effective Stress Consolidation Tests - Data | ESCG |
| [FGHG](#FGHG) | Field Geohydraulic Testing - General | LOCA |
| [FGHI](#FGHI) | Field Geohydraulic Testing - Instrumentation Details | FGHG |
| [FGHS](#FGHS) | Field Geohydraulic Testing - Test Results (per stage) | FGHG |
| [FGHT](#FGHT) | Field Geohydraulic Testing - Test Results | FGHI |
| [FLSH](#FLSH) | Drilling Flush Details | LOCA |
| [FRAC](#FRAC) | Fracture Spacing | LOCA |
| [FRST](#FRST) | Frost Susceptibility Tests | SAMP |
| [GCHM](#GCHM) | Geotechnical Chemistry Testing | This group is reserved for soil / water chemistry testing associated with geotechnical design assessments. Environmental contamination testing should be recorded in Group <del>ERES</del> ELRGSAMP |
| [GEOL](#GEOL) | Field Geological Descriptions | LOCA |
| [GRAG](#GRAG) | Particle Size Distribution Analysis - General | SAMP |
| [GRAT](#GRAT) | Particle Size Distribution Analysis - Data |GRAG |
| [HDIA](#HDIA) | Hole Diameter by Depth | LOCA |
| [HDPH](#HDPH) | Depth Related Exploratory Hole Information | LOCA |
| [HORN](#HORN) | Exploratory Hole Orientation and Inclination | LOCA |
| [ICBR](#ICBR) | In Situ California Bearing Ratio Tests | LOCA |
| [IDEN](#IDEN) | In Situ Density Tests | LOCA |
| [IFID](#IFID) | On Site Volatile Headspace Testing Using Flame Ionisation Detector | LOCA |
| [IPEN](#IPEN) | In Situ Hand Penetrometer Tests | LOCA |
| [IPID](#IPID) | On Site Volatile Headspace Testing by Photo Ionisation Detector | LOCA |
| [<del>IPRG</del>](#IPRG) | <del>In Situ Permeability Tests - General</del> | This group has been deprecated, see FGHG | <del>LOCA</del> |
| [<del>IPRT</del>](#IPRT) | <del>In Situ Permeability Tests - Data</del> | This group has been deprecated, see FGHT | <del>IPRG</del> |
| [IRDX](#IRDX) | In Situ Redox Tests | LOCA |
| [IRES](#IRES) | In Situ Resistivity Tests | LOCA |
| [ISAG](#ISAG) | Soakaway Tests - General | LOCA |
| [ISAT](#ISAT) | Soakaway Tests - Data | ISAG |
| [ISPT](#ISPT) | Standard Penetration Test Results LOCA |
| [IVAN](#IVAN) | In Situ Vane Tests LOCA |
| [LBSG](#LBSG) | Testing Schedule | - |
| [LBST](#LBST) | Testing Schedule Details | LBSG |
| [LDEN](#LDEN) | Density TestsSAMP |
| [LDYN](#LDYN) | Dynamic TestingSAMP |
| [LFCN](#LFCN) | Laboratory Fall Cone TestSAMP |
| [LLIN](#LLIN) | Linear Shrinkage TestsSAMP |
| [LLPL](#LLPL) | Liquid and Plastic Limit TestsSAMP |
| [LNMC](#LNMC) | Water/moisture Content TestsSAMP |
| [LOCA](#LOCA) | Location Details | PROJ |
| [LPDN](#LPDN) | Particle Density TestsSAMP |
| [LPEN](#LPEN) | Laboratory Hand Penetrometer TestsSAMP |
| [LRES](#LRES) | Laboratory Resistivity TestsSAMP |
| [LSLT](#LSLT) | Shrinkage Limit TestsSAMP |
| [LSTG](#LSTG) | Initial Consumption of Lime Tests - GeneralSAMP |
| [LSTT](#LSTT) | Initial Consumption of Lime Tests - Data | LSTG |
| [LSWL](#LSWL) | Swelling Index TestingSAMP |
| [LTCH](#LTCH) | Laboratory Thermal ConductivitySAMP |
| [LUCT](#LUCT) | Laboratory Unconfined Compression TestSAMP |
| [LVAN](#LVAN) | Laboratory Vane TestsSAMP |
| [MCVG](#MCVG) | MCV Tests - GeneralSAMP |
| [MCVT](#MCVT) | MCV Tests - Data | MCVG |
| [MOND](#MOND) | Monitoring Readings | MONG |
| [MONG](#MONG) | Monitoring Installations and Instruments LOCA |
| [PIPE](#PIPE) | Monitoring Installation Pipe Work LOCA |
| [PLTG](#PLTG) | Plate Loading Tests - General LOCA |
| [PLTT](#PLTT) | Plate Loading Tests - Data | PLTG |
| [PMTD](#PMTD) | Pressuremeter Test Data | PMTG |
| [PMTG](#PMTG) | Pressuremeter Test Results - General LOCA |
| [PMTL](#PMTL) | Pressuremeter Test Results - Individual Loops | PMTG |
| [PREM](#PREM) | Project Specific Time Related Remarks | - |
| [PTIM](#PTIM) | Boring/Drilling Progress by Time LOCA |
| [PTST](#PTST) | Laboratory Permeability TestsSAMP |
| [PUMG](#PUMG) | Pumping Tests - General LOCA |
| [PUMT](#PUMT) | Pumping Tests - Data | PUMG |
| [RCAG](#RCAG) | Rock Abrasiveness Tests - GeneralSAMP |
| [RCAT](#RCAT) | Rock Abrasiveness Tests - Data | RCAG |
| [RCCV](#RCCV) | Chalk Crushing Value TestsSAMP |
| [RDEN](#RDEN) | Rock Porosity and Density TestsSAMP |
| [RELD](#RELD) | Relative Density TestsSAMP |
| [RESC](#RESC) | Resonant Column Test - Consolidation | RESG |
| [RESD](#RESD) | Resonant Column Test - Data | RESG |
| [RESG](#RESG) | Resonant Column Test – GeneralSAMP |
| [RESP](#RESP) | Resonant Column Test - Derived Parameters | RESD |
| [RESS](#RESS) | Resonant Column Test - Saturation | RESG |
| [RPLT](#RPLT) | Point Load TestingSAMP |
| [RSCH](#RSCH) | Schmidt Rebound Hardness TestsSAMP |
| [RSHR](#RSHR) | Shore Scleroscope Hardness TestsSAMP |
| [RTEN](#RTEN) | Tensile Strength TestingSAMP |
| [RUCS](#RUCS) | Rock Uniaxial Compressive Strength and Deformability TestsSAMP |
| [RWCO](#RWCO) | Water Content of Rock TestsSAMP |
| [SAMP](#SAMP) | Sample Information || LOCA |
| [SCDG](#SCDG) | Static Cone Dissipation Tests - General | SCPG |
| [SCDT](#SCDT) | Static Cone Dissipation Tests - Data | SCDG |
| [SCPG](#SCPG) | Static Cone Penetration Tests - General LOCA |
| [SCPP](#SCPP) | Static Cone Penetration Tests - Derived Parameters | SCPG |
| [SCPT](#SCPT) | Static Cone Penetration Tests - Data | SCPG |
| [SHBG](#SHBG) | Shear Box Testing - GeneralSAMP |
| [SHBT](#SHBT) | Shear Box Testing - Data | SHBG |
| [STND](#STND) | Standards / Specifications | - |
| [SUCT](#SUCT) | Suction TestsSAMP |
| [TNPC](#TNPC) | Ten Per Cent FinesSAMP |
| [TREG](#TREG) | Triaxial Tests - Effective Stress - GeneralSAMP |
| [TRET](#TRET) | Triaxial Tests - Effective Stress - Data | TREG |
| [TREM](#TREM) | Location Specific Time Related Remarks LOCA |
| [TRIG](#TRIG) | Triaxial Tests - Total Stress - GeneralSAMP |
| [TRIT](#TRIT) | Triaxial Tests - Total Stress - Data | TRIG |
| [WADD](#WADD) | Water Added Records LOCA |
| [WETH](#WETH) | Weathering LOCA |
| [WGPG](#WGPG) | Wireline Geophysics - General LOCA |
| [WGPT](#WGPR) | Wireline Geophysics - Readings | WGPG |
| [WINS](#WINS) | Dynamic Sampling Run Details LOCA |
| [WSTG](#WSTG) | Water Strike - General LOCA |
| [WSTD](#WSTD) | Water Strike - Details | WSTG |