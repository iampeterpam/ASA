# AD-Joined Attributes Config

1. Add attribute to the Okta profile template
2. Map AD attributes to Okta profiles
3. Add attribute to the Advanced Server Access profile template
4. Map Okta profile attributes to Advanced Server Access profile attributes

# 1. Add attribute to the Okta profile template
    a. Directory > Profile Editor > User (default)
        - Add Attribute
        - Data type: string array
        - Display name: Active Directory Identity
        - Variable name: `activeDirectoryIdentity`
        - Description: Comma-separated list of AD accounts available to an Okta user. Users must manually enter a password when using these accounts.
        - User Permission: Read-Wriite
        - Save
        - Click on the pencil icon next to this new attribute
        - Source priority: Inherit from Okta
        - Save Attribute
        
    b. Directory > Profile Editor > User (default)
        - Add Attribute
        - Data type: string array
        - Display name: Active Directory Passwordless Identity
        - Variable name: `activeDirectoryPasswordlessIdentity`
        - Description: Comma-separated list of AD accounts available to an Okta user. Users don't need to enter a password when using these accounts.
        - User Permission: Read-Wriite
        - Source priority: Inherit from Okta
        - Save Attribute
        
# 2. Map AD Attributes to Okta profiles
    a. Directory > Profile Editor > Directories > Select Mappings next to AD
    b. In the AD to Okta User Tab, scroll down to activeDirectoryPasswordlessIdentity and paste in the following expression in the empty box:
    
    `Arrays.add(Arrays.toCsvString({}),appuser.userName)`
    c. Save Mappings

# 3. Add attribute to the Advanced Server Access Profile Template
    a. Directory > Profile Editor > Select Okta Advanced Server Access User
    b. Check at the bottom of the Attributes page to see if the following 2 attributes are listed: 
       i. `activeDirectoryIdentity`
      ii. `activeDirectoryPasswordlessIdentity`
        
# 4.Map Okta Profile Attributes to Advanced Server Access Profile Attributes
    a. Directory > Profile Editor > Click on **Mappings** next to **Okta Advanced Server Access User**
    b. Click on the **Okta User to Okta Advanced Server Access** Tab at the top
    c. Add `user.activeDirectoryIdentity` to the box on the left of activeDirectoryIdentity
    d. Add `user.activeDirectoryPasswordlessIdentity` to the box on the left of activeDirectoryPasswordlessIdentity
    e. Save Mappings
