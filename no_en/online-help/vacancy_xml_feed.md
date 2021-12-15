# Vacancy XML Feed

Via RESTful (webservice) EasyCruit allows you to connect to our system and pull data in the standardised XML format. This is the most popular method of connection, as it allows for fast and easy integration with EasyCruit.

We provide you a unique URL, solely for job postings to you, containing active jobs in XML format.

## Type of Feed

The EasyCruit RESTful service provides a live, real-time feed. This means that independent on your preferred option to define the posting duration (defined posting interval or custom dates); all requests will stay in the XML for that time frame that has been set by the customer when posting the job. Example: if the user selected January, 2nd as posting start date and January, 20th as posting end date, then the request will be listed in the XML from Jan, 2nd until Jan, 20th. After the 20th it will be removed from the feed. Hence: the list of jobs posted on your side, provided by EasyCruit should always represent a copy of postings listed in the feed. If a customer un-posts a job, then this job will be removed from the XML.

### Posting Period

EasyCruit supports multiple posting periods that can be picked by the user. Per standard we offer i.e. 30 days. We do support custom posting start and end dates as well.

#### Listing XML

<Vacancy id="xxxxxx" date_start="yyyy-mm-dd" date_end="yyyy-mm-dd" reference_number="">

<Versions>

<Version language="en"> (Vacancy language, ex. da, sv, gb, etc.)

<Title>Mandatory title</Title>

<TitleHeading>Not mandatory sub title</TitleHeading>

<AlternativeCompanyName>Company name</AlternativeCompanyName>

<ApplicationDeadline>Free text field with application deadline</ApplicationDeadline>

<Location>Free text field with job location</Location>

<Engagement>Free text field with engagement</Engagement>

<Region>

<Country id="xx" name="Sweden"> (Vacancy country)

<County id="xxx">Region in selected country</County>

</Country>

</Region>

<Categories>

<Item type="area-of-interest" id="xxx">Area of interest</Item>

<Item type="position-type" id="xxx">Position type</Item>

<Item type="job-level" id="xxx">Job level</Item>

<Item type="duration" id="xxx">Duration</Item>

<Item type="extent" id="xxx">Extent</Item>

<Item type="operating-time" id="xxx">Operation time</Item>

</Categories>

</Version>

</Versions>

<Departments>

<Department id="xxx">

<Name>Department name</Name>

<LogoURL>Full URL to uploaded logo</LogoURL>

<VacancyURL>URL to vacancy</VacancyURL>

<ApplicationURL>URL to application form</ApplicationURL>

</Department>

</Departments>

</Vacancy>

#### Vacancy XML

Besides the above variables these are the variables for the vacancy ad.

<Description>Vacancy text with html formatting included</Description>

<About>Department ingress with html formatting</About>

<PrivacyPolicy>Department Privacy Policy with html formatting</PrivacyPolicy>

<Address type="postal">(Department postal)

<Street>Street name / number</Street>

<Area>City</Area>

<AreaCode>Zip</AreaCode>

</Address>

<Address type="office">(Department visiting address)

<Street>Street name / number</Street>

<Area>City</Area>

<AreaCode>Zip</AreaCode>

</Address>

<Telephone type="office">Phone</Telephone>

<Telephone type="telefax">Fax</Telephone>

<ContactPersons>

<ContactPerson>

<CommonName>Contact person name</CommonName>

<Email>Contact person e-mail if published</Email>

<Telephone type="office">Contact person phone number</Telephone>

<Telephone type="cellular">Contact person cellular</Telephone>

</ContactPerson>

</ContactPersons>

<HomepageURL>Department web site address</HomepageURL>

<ImageURL>Full URL to uploaded image</ImageURL>

### Notes

There may be multiple instances of the following variables <Country>, <County>, <ContactPersons>, <Item

type="area-of-interest">, <Item type="position-type">, <Item type="job-level">, <Item type="duration">,<Item type="extent">, < Item type="operating-time"> in every vacancy.

Only mandatory variable is <Title>. Therefore other fields might be empty.

#### Multiple departments in the vacancy

An important feature of EasyCruit is that you can tie multiple departments on an ad. It would mean that the candidate is forced to choose a department before the post can be applied to. This feature will be implemented in the xml. Please contact EasyCruit Customer Success if you need to set up a test position with multiple departments.

#### Cache

There is a one hour cache of the XML feed from EasyCruit. Entries made in EasyCruit will only be visible one hour later unless the user uses the republish function.

#### Additional Information (XSD)

Listing:  [https://www.easycruit.com/dtd/vacancy-list.xsd](https://www.easycruit.com/dtd/vacancy-list.xsd)

Vacancy:  [https://www.easycruit.com/dtd/vacancy.xsd](https://www.easycruit.com/dtd/vacancy.xsd)

##### See also:

![](../Resources/Images/icon-document-link.png) [Import and Export of Vacancy Data](import_and_export_of_vacancy_data.htm)
![](../Resources/Images/icon-document-link.png) [Candidate API Methods](candidate_api_methods.htm)
![](../Resources/Images/icon-document-link.png) [Guide for Administrators - Integration/APIs](guide_for_administrators_integration_apis.htm)
![](../Resources/Images/icon-document-link.png) [Example Web Service Response](example_web_service_response.htm)
![](../Resources/Images/icon-document-link.png) [Guide for Administrators - Reports](guide_for_administrators_reports.htm)


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzNDAxNDI2NTFdfQ==
-->