# Open Refine Template for BCPL Remediation


## Template

#### Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```
####Body

```
<mods>
<identifier type="pid">{{cells["identifier"].value}}</identifier>
<identifier>{{cells["recordIdentifier"].value}}</identifier>
{{if(isBlank(cells['title'].value), '', '<titleInfo supplied="yes"><title>' + cells["title"].value + '</title></titleInfo>')}} 
{{if(isBlank(cells['date_photo'].value), '', '<originInfo><dateCreated>' + cells['date_photo'].value + '</dateCreated><dateCreated encoding="edtf" keyDate="yes">' + cells['date_photo'].value + '</dateCreated></originInfo>')}}
<abstract>{{cells["abstract"].value}}</abstract>
{{if(isBlank(cells['photographer'].value), '', '<name' + if(isBlank(cells['photographer_URI'].value), '', ' authority="naf" valueURI="' + cells['photographer_URI'].value + '"') + '><namePart>' + cells['photographer'].value + '</namePart><role>
<roleTerm type="text" authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/pht">Photographer</roleTerm>
</role></name>')}}
{{if(isBlank(cells['architect_creator'].value), '', '<name' + if(isBlank(cells['architect_creator_URI'].value), '', ' authority="naf" valueURI="' + cells['architect_creator_URI'].value + '"') + '><namePart>' + cells['architect_creator'].value + '</namePart><role>
<roleTerm type="text" authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/asn">Associated name</roleTerm>
</role></name>')}}
<physicalDescription><form authority="aat" valueURI="{{cells['form_URI'].value}}">{{cells['form'].value}}</form><digitalOrigin>reformatted digital</digitalOrigin></physicalDescription>
{{if(isBlank(cells['note'].value), '', '<note>' + cells['note'].value + '</note>')}}
{{if(isBlank(cells['note_2'].value), '', '<note>' + cells['note_2'].value + '</note>')}}
<subject authority="lcsh" valueURI="http://id.loc.gov/authorities/subjects/sh85101268"><topic>Architectural photography</topic></subject>
{{if(isBlank(cells['subject_topic'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject_topic_URI'].value + '"><topic>' + cells['subject_topic'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_topic_2'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject_topic_2_URI'].value + '"><topic>' + cells['subject_topic_2'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_name_2'].value), '', '<subject' + if(isBlank(cells['subject_name_2_URI'].value), '', ' authority="naf" valueURI="' + cells['subject_name_2_URI'].value + '"') + '><name><namePart>' + cells['subject_name_2'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['subject_name_3'].value), '', '<subject' + if(isBlank(cells['subject_name_3_URI'].value), '', ' authority="naf" valueURI="' + cells['subject_name_3_URI'].value + '"') + '><name><namePart>' + cells['subject_name_3'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['subject_geographic'].value), '', '<subject authority="' + cells['subject_geographic_authority'].value + '" valueURI="' + cells['subject_geographic_URI'].value + '"><geographic>' + cells['subject_geographic'].value + '</geographic><cartographics><coordinates>'+ cells['coordinates'].value + '</coordinates></cartographics></subject>')}}
{{if(isBlank(cells['subject_2_geographic'].value), '', '<subject><geographic>' + cells['subject_2_geographic'].value + '</geographic></subject>')}}
<language>
<languageTerm type="text" authority="iso639-2b">No linguistic content</languageTerm>
</language>
<typeOfResource>still image</typeOfResource>
<relatedItem displayLabel="Project" type="host"><titleInfo><title>{{cells['digital_collection'].value}}</title></titleInfo></relatedItem>
<location>
<physicalLocation>Blount County Public Library</physicalLocation>
</location>
<recordInfo>
<recordContentSource>Blount County Public Library</recordContentSource>
</recordInfo>
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
</mods>

```

#### Suffix

```
</modsCollection>
```