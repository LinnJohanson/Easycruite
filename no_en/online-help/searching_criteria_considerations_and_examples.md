# Searching Criteria Considerations and Examples

When setting up the search terms for search templates, there are a number of considerations that affect the results. If the expected search results are not being displayed, it could be due to the following issues:

-   Search terms must be a minimum of three characters in length and special characters such as "+" and "-" are not searchable characters, so are not included in the three character minimum. For example, the a programming skill like "C++" cannot be included in a free text search.
-   Common words, such as "and" or "name" are also excluded from searches.

There are a number of operators that can be included in the search criteria. This helps enable more focused searches and is made up of the following:

+

A plus sign indicates that the following word must be present

-

A negative sign indicates that the following word must not be present

( )

Parentheses enable words to be grouped together into sub-expressions

*

The asterisk is a wildcard that can be appended to the end or a search word.

"

A phrase contained within double quotes must be matched identically for it to be included in any search results.

To illustrate the information above, the following examples show how different search terms return different results:

sales dept

Returns results where at least one of the two words is found

+sales +dept

Returns results where both words are found

+sales dept - Returns results where "sales" is found, but ranks results higher that also contain "dept"

+sales -dept - Returns results where "sales" is found and "dept" is not

+sales ~dept - Returns results where "sales" is found, but ranks results lower that also contain "dept"

+sales +(>dept <exec) - Returns results that contain "sales" and "dept" or "sales" and "exec", in any order, however, "sales dept" would rank higher than "sales exec"

sales* - Returns results that contain words such as "sales", "salesman" or "salesperson"

"sales dept" - Returns results that contain the exact phrase "sales dept"


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2MTMyMTkwM119
-->