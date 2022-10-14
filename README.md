# Create fictive users

This little code snippet reads an Excel-file with fictive user info and injects the data into the MongoDB userinfo cash. Since the cash is always queried first when user info is requested by the app, fictive users can be handled just like real users. The update time for the cash is also set to the far future so the user information will always be regarded as "fresh".

The Excel-file consist of eigth fields with personal information. "PersonId", "FirstName", "LastName", "GivenName", "Address", "ZipCode", "City" and "MunicipalityCode". These contents of these fields are identical to the information returned by KIR. The last fields are "PersonId" of a persons cildren. One "PersonId" per column. The children will be marked as having a releation type "B" (Barn) to the user. In the future, relation type "VF" (Vårdnadshavare För) will be added when needed.

Since this relation is bi-directional, i.e., the child will have a "FA" (Far) and/or "MO" (Mor) relation to the user in it's own user info. Therefor all cildren must also exits as users in the Excel-file.