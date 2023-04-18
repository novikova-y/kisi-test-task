# Information

## Product

- **Description:** Kisi is one of the major disruptive players in the access control industry, bringing a fully cloud based approach to managing and monitoring physical security for offices and many more highly frequented spaces.

## Prerequisites
Navigate to the [Kisi Web App](https://kisi-web-production-325414--qa-test-c8f0ybu9.web.app/users/sign_in)

## To go to 
* Users Settings Page - Login -> Users (in side navigation) -> Clicking on user row opens that user’s setting page.
* Groups Index Page - Login -> Groups (in side navigation) opens the Groups Index Page.
* Groups Settings Page - Login -> Groups (in side navigation) -> Clicking on group row opens that group’s setting page


# Groups Settings Page Test Cases

## General

- [Passed] Try editing the name and press "SAVE" button
  - It should reflect accordingly in Groups Index Page and Groups Settings Page
- [Passed] Try deleting the name and press "SAVE" button
  - Error message shows that name can't be blank
- [Failed] Try editing the description and press "SAVE" button
  - It should reflect accordingly in Groups Index Page and Groups Settings Page
- [Failed] Try deleting the description and press "SAVE" button
  - It should reflect accordingly in Groups Index Page and Groups Settings Page
- [Failed] Ensure that group can be deleted via the "DELETE" button
  - Toast message shows that group has been removed
  - It should reflect accordingly in Groups Index Page


### Issues
- [High] Try editing the description and press "SAVE" button
  - Toast message shows that group was updated successfully **but**
  - It doesn't reflect accordingly in Groups Index Page and Groups Settings Page
- [Medium] Try deleting the description and press "SAVE" button
  - Toast message shows that group was updated successfully **but**
  - It doesn't reflect accordingly in Groups Index Page and Groups Settings Page
- [Low] Ensure that group can be deleted via the "DELETE" button
  - Toast message shows that group removal failed **but**
  - It reflects accordingly in Groups Index Page

### Bug report

***Wrong toast message after group removal***

**Steps to Reproduce:**

1. Open the Groups Index Page
2. Open any group’s setting page
3. Click 'Delete' button on the upper right

**Expected Result:**

  - Toast message shows that group has been removed
  - It should reflect accordingly in Groups Index Page

**Actual Result:**

  - Toast message shows that group removal failed
  - It reflects accordingly in Groups Index Page

**Frequency**

Repeatable

**Severity**

Minor

**Enclosures**

[![2022-09-27-23-45-49.png](https://i.postimg.cc/VLSgg81c/2022-09-27-23-45-49.png)](https://postimg.cc/Xpb9Ntp2)


## Permissions

- [Failed] Ensure that restrictions can be toggled on and off
  - [Passed] Geofence Restriction
  - [Passed] Primary Device Restriction
  - [Passed] Kisi Reader Restriction
  - [Failed] Allow App Access

### Issues

- [High] Allow App Access restriction cannot be toggled off

### Bug report

***Allow App Access restriction cannot be toggled off***

**Steps to Reproduce:**

1. Open the Groups Index Page
2. Open any group’s setting page
3. Click 'Permissions' section
4. Click the toggle near 'Allow App Access' restriction
5. Click 'Save' button
6. Reload the page

**Expected Result:**

  - Toast message shows that group was updated successfully
  - Updates should reflect accordingly in Permissions section

**Actual Result:**

  - Toast message shows that group was updated successfully
  - Allow App Access restriction are always toggled on

**Frequency**

Repeatable

**Severity**

Major


## Doors

- [Passed] Try to add a door by clicking _ADD DOORS_ button
  - Ensure that you can only select one place at a time
  - Ensure that only doors related to the selected place are displayed in the "Search doors" dropdown
  - Ensure that selected doors are displayed below with the place's name
- [Passed] Try to remove the doors you have added by pressing the "cross" icon
  - Door is removed from the list
  - Ensure that the doors are reflected correctly on Doors tab in Groups Settings Page after adding
- [Passed] Try to add door that has been already added to the group
  - Popup with error message that door has not been added is displayed
- [Passed] Try to add several doors
  - Several doors can be added
  - Ensure that the doors are reflected correctly on resources list in Groups Settings Page after creating it
- [Passed] Each Door’s Geofence Restriction and Reader Restriction appear correctly and their corresponding tooltips as well.
- [Passed] Try to click on one of the door
  - It redirects a user to the door settings page
- [Passed] Ensure admin can delete the resource from the group by pressing the "trash can" icon
  - The door should be removed from the group and is reflected accordingly in the Groups Settings Page
  - Toast message shows that door has been removed
  - Door's Settings Page for the door should that the group has no access to it anymore
- [Passed] Ensure pagination works as it should
  - [ ] Previous page
  - [ ] Next page
  - "Page X of X" appropriate current page number/total amount of pages are shown

  
### Issues

- [Low] 'Add Dors' title on the popup
- [Medium] Popup with error message that door has not been added has 'Try again' button --> User could be stuck in an infinite loop. Error message should be more precise. **OR:**
- [Medium] When user has added several doors in the first iteration they are present on the list when user is adding new doors in second iteration --> that's why the previous situation happens. We can remove doors from the list of available doors as far as they are already added.

### Bug report

***'Add Dors' title on the popup***

**Steps to Reproduce:**

1. Open the Groups Index Page
2. Open any group’s setting page
3. Click 'Doors' section
4. Try to add a door by clicking _ADD DOORS_ button

**Expected Result:**

  - Popup will have a title with correct spelling
  
**Actual Result:**

  - Popup has 'Add Dors' title

**Frequency**

Repeatable

**Severity**

Enhancement

**Enclosures**

[![2022-09-28-00-44-19.png](https://i.postimg.cc/vB5NHwqn/2022-09-28-00-44-19.png)](https://postimg.cc/jwdXZmrq)

## Users Table

- [Passed] Ensure search function works
  - [Passed] Try searching for a user's name
  - [Passed] Try searching for a part of a user's name
  - [Passed] Try searching for an invalid name that doesn't match
    - Ensure it shows message "No users found"
  - [Passed] Try searching a random string and removing the content in search function
    - Ensure that the users list appears again
- [Failed] Ensure that admin can delete the user from the group by selecting user and then pressing on Remove From Group button and confirming in the dialog
  - The user should be removed from the group and is reflected accordingly in the Groups Settings Page
  - Toast message shows that user has been removed
  - Users Settings Page for that user should show that the user has no access to the group
- [Passed] Ensure that pressing on the user row will open up the Update Group Membership popup screen
- [Passed] When sharing access ensure that the user role with respect to the group is shown correctly in the role column of users table.
- [Passed] Suspending a user in User settings page should reflect correctly in this page
- [Passed] Ensure pagination works as it should
  - [Passed] Previous page
  - [Passed] Next page
  - "Page X of X" appropriate current page number/total amount of pages are shown

### Bug report

***Admin cannot delete the user from the group***

**Steps to Reproduce:**

1. Open the Groups Index Page
2. Open any group’s setting page
3. Choose any user from the group
4. Select user and then press on Remove From Group button and confirm in the dialog

**Expected Result:**

 - The user should be removed from the group and is reflected accordingly in the Groups Settings Page
  - Toast message shows that user has been removed
  - Users Settings Page for that user should show that the user has no access to the group
  
**Actual Result:**

 - Toast message shows that user has been removed
 - The user is not removed from the group and is not reflected accordingly in the Groups Settings Page
  - Users Settings Page for that user show that the user has an access to the group

**Frequency**

Repeatable

**Severity**

Major


## Users - Share Access Dialog

- [Failed] Try to add an invalid email address (e.g a@a OR abcd) and press enter
  - Email address will not be added
- [Passed] Try to click _ADD_ with empty "Email" field
  - _ADD_ button remains disabled
- [Passed] Ensure that the default access states when the popup appears are correct
  - "Send Invite Email" toggled on
- [Passed] Try to share access to a user with "Send Invite Email" toggled on 
  - User should receive an email that includes "Sign in to unlock" 
- [Passed] Try to share access to a user with "Send Invite Email" toggled off
  - User should not receive any email
- [Passed] Add a user with Basic User permissions
- [Failed] Check the date picker for the basic permissions
  - [Passed] The end time cannot be earlier than the start time and dialog disallows you from doing so
  - [Passed] You should be allowed to save validity settings with either the start/end time missing
  - [Failed] Ensure that the current time will appear automatically when entering the start/end date to the text field
  - [Passed] Ensure that "Clear" button become enabled when start/end date text fields are not empty
  - [Passed] Ensure that "Clear" button removes entered date and time
  - [Passed] Ensure that the group is reflected under the Users Settings Page of that user
  - [Passed] Ensure that the user is reflected in the users list of the Groups Settings Page
- [Passed] Ensure that timezone value matches with browser timezone
- [Failed] Add a user with basic permissions who has time validity
  - Ensure that user is no longer a member in the group after the time validity ends
- [Failed] Add a user with Group Administrator permissions
  - User is added to the group with Group Administrator permissions

 ### Issues

- [Medium] Try to add an invalid email address (e.g a@a OR abcd) and press enter
  - Invalid email address can be added
- [Medium] Ensure that the current time will appear automatically when entering the start/end date to the text field
  - If I've started entering date at 10:46pm and now current time has changed and it's 10:48pm, current time for end date still be 10:46, not 10:48
- [High] Add a user with basic permissions who has time validity
  - Ensure that user is no longer a member in the group after the time validity ends --> I've tried setting end time and then changing my system time – nothing happened; when I'm trying to set end date to today but some minutes later it cannot be saved – end date automatically sets to +7 days (and I cannot check it)
- [High] Add a user with Group Administrator permissions
  - There is no option to add a user with Group Administrator permissions

### Bug report

***No option to add a user with Group Administrator permissions***

**Steps to Reproduce:**

1. Open the Groups Index Page
2. Open any group’s setting page
3. Click 'Share Access' button on top of the Users table
4. Add any email address
5. Click three dots sign near 'Role: Basic Permissions" section
 

**Expected Result:**

  - There would be an option to add a user with Group Administrator permissions
     
**Actual Result:**

  - There are only two options to add a user with Basic or Manager permissions

**Frequency**

Repeatable

**Severity**

Major? (depends on specs)

# Users Settings Page Test Cases


## General

- [Passed] Try editing the name and press "SAVE" button
  - Toast message shows that user was updated successfully
  - It should reflect accordingly in Users Index Page and Users Settings Page
- [Passed] Try deleting the name and press "SAVE" button
  - Error message shows that name can't be blank
- [Failed] Try adding the photo 
  - [Passed] Try adding the photo from your computer, cropping it and pressing "SAVE" button
  - [Failed] Ensure that after saving the photo and page reloading the uploaded photo is present
- [Passed] Try adding the Notes field and press "SAVE" button
  - Toast message shows that user was updated successfully
  - It should reflect accordingly in User Settings Page
- [Passed] Try clearing the Notes field and press "SAVE" button
  - Toast message shows that user was updated successfully
  - It should reflect accordingly in User Settings Page
- [Passed] Ensure that user can be deleted via the "DELETE" button and confirming in the dialog
  - Toast message shows that user has been removed
  - It should reflect accordingly in Users Index Page

  
## Permissions

- [Failed] Ensure that changing the role reflects accordingly in Users Index Page
  - [Passed] Toast message shows that user was updated successfully
  - [Failed] Basic
  - [Failed] Manager
  - [Failed] Administrator
- [Passed] Ensure that 'Suspend Access' can be toggled on and off


## Groups

- [Passed] Try to add a user to a group by clicking _Share Access_ button
  - Ensure that you can only select one group at a time
  - Ensure that selected group is displayed in 'Search Groups' field
  - Toast message shows that share was created successfully
  - Ensure that the user is reflected correctly on list in Groups Index Page and Groups Settings Page after adding him
- [Passed] Try to remove the group you have added user to by pressing the "Trash" icon
  - Toast message shows that membership was deleted successfully
  - Ensure that the group is removed from the list
  - Ensure that the users are reflected correctly on users table in Groups Settings Page after adding
- [Passed] Try to add user to a group he has been already been added to
  - Error message that the record already exists displayed
- [Passed] Try to add several groups
  - Several groups can be added
  - Ensure that the users are reflected correctly on users table in Groups Settings Page after adding them
- [Passed] Ensure that the default access states when the popup appears are correct
  - "Send Invite Email" toggled on
- [Failed] Try to share access to a user with "Send Email with Updates" toggled on 
  - User should receive an email to the user explaining the membership changes (user receives an email that includes "Sign in to unlock", not the membership changes)
- [Passed] Try to share access to a user with "Send Email with Updates" toggled off
  - User should not receive any email
- [Failed] Ensure that changing the role reflects accordingly in Users table Page in Groups Settings Page and Users Index Page
  - [Passed] Toast message shows that user was updated successfully

  
  
# Improvements that I would make to existing test cases

1. Prepare a list of user scenarios 
2. Make test cases into a table like this (to make it more readable):

| \#  | Description | Test steps  | Expected Result  | Actual Result    | Status |
| --- | ----------- | ------------| ---------------- | ---------------- |--------|
| 1   |             |             |                  |                  |        |

3. Unique description for each test case
4. Add more detailed testing steps - it can be difficult for someone who has never seen the app or is seeing it for the first time to reproduce cases.
5. Add 'Actual Result' column/field – it was hard for me to justify why I considered a case a failure.
6. Provide test cases to the stakeholders and ask for their feedback!
