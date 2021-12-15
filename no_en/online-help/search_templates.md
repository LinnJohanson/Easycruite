# Search Templates

Search templates enable EasyCruit administrators to create templates that recruiters can use for searching the applicant database. This functionality is useful for companies that have a large number of registered applicants or when searching for a very specific skill set. Depending on the option that is included in the search template, the values can be entered in free text fields, selected from populated lists, the results of questions and uploaded files.

For example, the  Work Experience  section of the search templates provides the user with the ability to select from dropdown lists, multiple select dropdown lists and free text fields.

For information on running searches refer to  [Searching for Candidates](../getting-started/searching_for_candidates.htm).

![Closed](../Skins/Default/Stylesheets/Images/transparent.gif)Creating a Search Template

1.  From the  Toolbar  click  Settings  then  Search Template.
2.  To create a brand new search template, ensure the  Choose Search Template  list is set to  Select  
    - or -  
    to base the search template on an existing template, select it from the  Choose Search Template  list.
3.  Enter a name for the search template in the  Save Search as  field.
4.  Click the arrow next to each of the headings to expand the options available in that section.
5.  Select the required values for the search parameters.  
    For each section that has had search parameters selected, a red asterisk is placed in the heading row.
6.  Click  Save Template  to save the new template.

![Closed](../Skins/Default/Stylesheets/Images/transparent.gif)Editing an Existing Search Template

1.  From the  Toolbar  click  Settings  then  Search Templates.
2.  Select the template to be edited from the  Choose Search Template  list.
3.  Click the arrow next to each of the headings to expand the options available in that section.  
    The search template is displayed showing the same section that was expanded the last time it was saved.
4.  Select the required values for the search parameters.
5.  Click  Update Template  to save the changes.

![Closed](../Skins/Default/Stylesheets/Images/transparent.gif)Deleting a Search Template

1.  From the  Toolbar  click  Settings  then  Search Templates.
2.  Select the template to be deleted from the  Choose Search Template  list.
3.  Click  Delete Template  then click  OK  when prompted to confirm the deletion.

![Closed](../Skins/Default/Stylesheets/Images/transparent.gif)Using Quick Links for Searching

1.  From the  Start  page click the plus icon to expand the  Quick Links to Search  box.
2.  Click the required search item from the list of  Search Templates  or  Saved Searches  to display the advanced  Candidate Search  page.
3.  Complete the search as required.  
    The Quick Links search option is not available by default and must be enabled in your system.

![Closed](../Skins/Default/Stylesheets/Images/transparent.gif)Search Criteria Considerations and Examples

When setting up the search terms for search templates, there are a number of considerations that affect the results. If the expected search results are not being displayed, it could be due to the following issues:

Search terms must be a minimum of three characters in length and special characters such as "+" and "-" are not searchable characters, so are not included in the three character minimum. For example, the a programming skill like "C++" cannot be included in a free text search.

-   Common words, such as "and" or "name" are also excluded from searches.

There are a number of operators that can be included in the search criteria. This helps enable more focused searches and is made up of the following:

.+ : A plus sign indicates that the following word must be present

.**-** : A negative sign indicates that the following word must not be present

**()** : Parentheses enable words to be grouped together into sub-expressions

.***** : The asterisk is a wildcard that can be appended to the end or a search word.

**"** : A phrase contained within double quotes must be matched identically for it to be included in any search results.

To illustrate the information above, the following examples show how different search terms return different results:

**sales dept** - Returns results where at least one of the two words is found

**+sales +dept** - Returns results where both words are found

**+sales dept** - Returns results where "sales" is found, but ranks results higher that also contain "dept"

**+sales -dept** - Returns results where "sales" is found and "dept" is not

**+sales ~dept** - Returns results where "sales" is found, but ranks results lower that also contain "dept"

**+sales +(>dept <exec)** - Returns results that contain "sales" and "dept" or "sales" and "exec", in any order, however, "sales dept" would rank higher than "sales exec"

**sales*** - Returns results that contain words such as "sales", "salesman" or "salesperson"

**"sales dept"** - Returns results that contain the exact phrase "sales dept"

##### See also:

![](../Resources/Images/icon-document-link.png) [Searching for Candidates](searching_for_candidates.htm)
![](../Resources/Images/icon-document-link.png) [Job Categories](job_categories.htm)
![](../Resources/Images/icon-document-link.png) [Additional Questions](additional_questions.htm)
![](../Resources/Images/icon-document-link.png) [Users: Create, Edit, Delete](users_create_edit_delete.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MzYwMzMzMDddfQ==
-->