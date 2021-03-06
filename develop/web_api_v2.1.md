# Web API (For Seafile server v5.1.0+)


<p>
<div class="toc">
<ul>

<li>
<a href="#seafile-web-api">Seafile Web API</a>
<ul>

    <li><a href="#api-basics">API Basics</a></li>
    <li><a href="#status-code">Status Code</a></li>
    <li><a href="#quick-start">Quick Start</a></li>

    <li>
        <a href="#account">Account</a>
        <ul>
            <li><a href="#check-account-info">Check Account Info</a></li>
            <li><a href="#server-info">Get Server Information</a></li>
        </ul>
    </li>

    <li>
        <a href="#starred-files">Starred Files</a>
        <ul>
            <li><a href="#list-starred-files">List starred files</a></li>
            <li><a href="#star-a-file">Star A File</a></li>
            <li><a href="#unstar-a-file">Unstar A File</a></li>
        </ul>
    </li>

    <li>
        <a href="#group">Group</a>
        <ul>
            <li><a href="#list-groups">List Groups</a></li>
            <li><a href="#add-a-group">Add a Group</a></li>
            <li><a href="#get-info-of-a-group">Get Info of a Group</a></li>
            <li><a href="#rename-a-group">Rename a Group</a></li>
            <li><a href="#transfer-a-group">Transfer a Group</a></li>
            <li><a href="#delete-a-group">Delete a Group</a></li>
            <li><a href="#quit-group">Quit Group</a></li>
            <li>
                <a href="#group-member">Group Member</a>
                <ul>
                    <li><a href="#list-group-members">List Group Members</a></li>
                    <li><a href="#add-a-group-member">Add a Group Member</a></li>
                    <li><a href="#bulk-add-group-members">Bulk Add Group Members</a></li>
                    <li><a href="#get-info-of-a-group-member">Get Info of a Group Member</a></li>
                    <li><a href="#set-a-group-member-admin">Set a Group Member Admin</a></li>
                    <li><a href="#unset-a-group-member-admin">Unset a Group Member Admin</a></li>
                    <li><a href="#delete-a-group-member">Delete a Group Member</a></li>
                </ul>
            </li>
            <li>
                <a href="#group-message">Group Message</a>
                <ul>
                    <li><a href="#get-group-messages">Get Group Messages</a></li>
                    <li><a href="#send-a-group-message">Send A Group Message</a></li>
                    <li><a href="#delete-a-group-message">Delete A Group Message</a></li>
                </ul>
            </li>
        </ul>
    </li>

    <li>
        <a href="#share">Share</a>
        <ul>
            <li>
                <a href="#share-link">Share Link</a>
                <ul>
                    <li><a href="#list-all-share-links">List all Share Links</a></li>
                    <li><a href="#list-share-links-of-a-library">List Share Links of a Library</a></li>
                    <li><a href="#list-share-link-of-a-folder-file">List Share Link of a Folder(File)</a></li>
                    <li><a href="#create-share-link">Create Share Link</a></li>
                    <li><a href="#delete-share-link">Delete Share Link</a></li>
                    <li><a href="#send-share-link-email">Send Share Link Email</a></li>
                    <li><a href="#list-direntry-in-dir-download-link">List Direntry in Dir Download Link</a></li>
                </ul>
            </li>
            <li>
                <a href="#upload-link">Upload Link</a>
                <ul>
                    <li><a href="#list-upload-links">List Upload Links</a></li>
                    <li><a href="#create-upload-link">Create Upload Link</a></li>
                    <li><a href="#delete-upload-link">Delete Upload Link</a></li>
                    <li><a href="#send-upload-link-email">Send Upload Link Email</a></li>
                </ul>
            </li>
            <li>
                <a href="#shared-libraries">Shared Libraries</a>
                <ul>
                    <li><a href="#list-user-shared-libraries">List User Shared Libraries</a></li>
                    <li><a href="#list-group-shared-libraries">List Group Shared Libraries</a></li>
                    <li><a href="#list-be-shared-libraries">List Be Shared Libraries</a></li>
                    <li><a href="#delete-be-shared-library">Delete Be Shared Library</a></li>
                    <li><a href="#share-a-library-to-user">Share a Library to User</a></li>
                    <li><a href="#unshare-a-library-from-user">Unshare a Library from User</a></li>
                    <li><a href="#update-permission-of-user-shared-library">Update Permission of User Shared Library</a></li>
                    <li><a href="#share-a-library-to-group">Share a Library to Group</a></li>
                    <li><a href="#unshare-a-library-from-group">Unshare a Library from Group</a></li>
                    <li><a href="#update-permission-of-group-shared-library">Update Permission of Group Shared Library</a></li>
                </ul>
            <li>
                <a href="#shared-folders">Shared Folders</a>
                <ul>
                    <li><a href="#share-a-folder">Share A Folder</a></li>
                    <li><a href="#list-shared-folders">List Shared Folders</a></li>
                    <li><a href="#update-shared-folder-permission">Update Shared Folder Permission</a></li>
                    <li><a href="#unshare-a-folder">Unshare A Folder</a></li>
                </ul>
            </li>
            </li>
        </ul>
    </li>

    <li>
        <a href="#library">Library</a>
        <ul>
            <li><a href="#get-default-lib">Get Default Library</a></li>
            <li><a href="#create-default-lib">Create Default Library</a></li>
            <li><a href="#list-libraries">List Libraries</a></li>
            <li><a href="#get-library-info">Get Library Info</a></li>
            <li><a href="#get-library-owner">Get Library Owner</a></li>
            <li><a href="#get-library-history">Get Library History</a></li>
            <li><a href="#get-library-history-limit-days">Get Library History Limit Days</a></li>
            <li><a href="#set-library-history-limit-days">Set Library History Limit Days</a></li>
            <li><a href="#create-library">Create Library</a></li>
            <li><a href="#check/create-sub-library">Check/Create Sub Library</a></li>
            <li><a href="#delete-library">Delete Library</a></li>
            <li><a href="#rename-library">Rename Library</a></li>
            <li><a href="#transfer-library">Transfer Library</a></li>
            <li><a href="#decrypt-library">Decrypt Library</a></li>
            <li><a href="#create-public-lib">Create Public Library</a></li>
            <li><a href="#set-exist-lib-as-public-lib">Set Exist Lib as Public Library</a></li>
            <li><a href="#remove-public-lib">Remove Public Library</a></li>
            <li><a href="#fetch-library-download-info">Fetch library download info</a></li>
            <li><a href="#search-files-in-libraries">Search Files in Libraries</a></li>
            <li><a href="#get-library-download-links">Get Library Download Links</a></li>
            <li><a href="#get-library-upload-links">Get Library Upload Links</a></li>
            <li><a href="#delete-library-download-link">Delete Library Download Link</a></li>
            <li><a href="#delete-library-upload-link">Delete Library Upload Link</a></li>
        </ul>
    </li>

    <li>
        <a href="#file">File</a>
        <ul>
            <li><a href="#view-file-through-owa">View File Through Owa</a></li>
            <li><a href="#download-file">Download File</a></li>
            <li><a href="#get-file-detail">Get File Detail</a></li>
            <li><a href="#get-file-history">Get File History</a></li>
            <li><a href="#restore-file-from-history">Restore File From History</a></li>
            <li><a href="#download-file-revision">Download File From a Revision</a></li>
            <li><a href="#create-file">Create File</a></li>
            <li><a href="#rename-file">Rename File</a></li>
            <li><a href="#lock-file">Lock File</a></li>
            <li><a href="#unlock-file">Unlock File</a></li>
            <li><a href="#move-file">Move File</a></li>
            <li><a href="#copy-file">Copy File</a></li>
            <li><a href="#revert-file">Revert File</a></li>
            <li><a href="#delete-file">Delete File</a></li>
            <li>
                <a href="#upload-file">Upload File</a>
                <ul>
                    <li><a href="#get-upload-link">Get Upload Link</a></li>
                    <li><a href="#upload-file-1">Upload File</a></li>
                </ul>
            </li>
            <li>
                <a href="#update-file">Update file</a>
                <ul>
                    <li><a href="#get-update-link">Get Update Link</a></li>
                    <li><a href="#update-file-1">Update File</a></li>
                </ul>
            </li>
            <li><a href="#get-upload-blocks-link">Get Upload Blocks Link</a></li>
            <li><a href="#get-update-blocks-link">Get Update Blocks Link</a></li>
        </ul>
    </li>

    <li>
        <a href="#directory">Directory</a>
        <ul>
            <li><a href="#list-directory-entries">List Directory Entries</a></li>
            <li><a href="#create-new-directory">Create New Directory</a></li>
            <li><a href="#rename-directory">Rename Directory</a></li>
            <li><a href="#delete-directory">Delete Directory</a></li>
            <li><a href="#download-directory">Download Directory</a></li>
            <li><a href="#revert-directory">Revert Directory</a></li>
        </ul>
    </li>

    <li>
        <a href="#multiple-files-directories">Multiple Files / Directories</a>
        <ul>
            <li><a href="#multiple-files-directories-copy">Copy</a></li>
            <li><a href="#multiple-files-directories-move">Move</a></li>
            <li><a href="#multiple-files-directories-delete">Delete</a></li>
            <li><a href="#multiple-files-directories-download">Download</a></li>
        </ul>
    </li>

    <li>
        <a href="#avatar">Avatar</a>
        <ul>
            <li><a href="#get-user-avatar">Get User Avatar</a></li>
            <li><a href="#get-group-avatar">Get Group Avatar</a></li>
        </ul>
    </li>

    <li>
        <a href="#devices">Devices</a>
        <ul>
            <li><a href="#get-user-devices">Get User Devices</a></li>
            <li><a href="#unlink-user-device">Unlink User Device</a></li>
        </ul>
    </li>

    <li><a href="#get-file-activities">Get File Activities</a></li>
    <li><a href="#get-thumbnail-image">Get Thumbnail Image</a></li>
    <li><a href="#search-user">Search User</a></li>

</ul>
</li>

<li>
<a href="#admin-only">Admin Only</a>
<ul>
    <li>
        <a href="#admin-only-account">Account</a>
        <ul>
            <li><a href="#admin-only-list-accounts">List Accounts</a></li>
            <li><a href="#admin-only-get-account">Get Account Info</a></li>
            <li><a href="#admin-only-create-account">Create Account</a></li>
            <li><a href="#admin-only-update-account">Update Account</a></li>
            <li><a href="#admin-only-migrate-account">Migrate Account</a></li>
            <li><a href="#admin-only-delete-account">Delete Account</a></li>
        </ul>
    </li>

    <li>
        <a href="#admin-only-devices">Devices</a>
        <ul>
            <li><a href="#admin-only-get-desktop-devices">Get Desktop Devices</a></li>
            <li><a href="#admin-only-get-mobile-devices">Get Mobile Devices</a></li>
            <li><a href="#admin-only-unlink-user-device">Unlink User Device</a></li>
            <li><a href="#admin-only-get-device-errors">Get Device Errors</a></li>
            <li><a href="#admin-only-clean-device-errors">Clean Device Errors</a></li>
        </ul>
    </li>

    <li>
        <a href="#admin-only-default-library">Default Library</a>
        <ul>
            <li><a href="#admin-only-get-user-default-library">Get User Default Library</a></li>
            <li><a href="#admin-only-create-user-default-library">Create User Default Library</a></li>
        </ul>
    </li>

    <li>
        <a href="#admin-only-libraries">Librairies</a>
        <ul>
            <li><a href="#admin-only-get-all-libraries">Get all Libraries</a></li>
            <li><a href="#admin-only-search-library-by-name">Search Library by Name</a></li>
            <li><a href="#admin-only-search-library-by-owner">Search Library by Owner</a></li>
            <li><a href="#admin-only-delete-a-library">Delete a Library</a></li>
            <li><a href="#admin-only-transfer-a-library">Transfer a Library</a></li>
            <li><a href="#admin-only-get-library-dirents">Get Library Dirents</a></li>
        </ul>
    </li>

    <li>
        <a href="#admin-only-shares">Shares</a>
        <ul>
            <li><a href="#admin-only-get-repo-user-shares">Get Repo User Shares</a></li>
            <li><a href="#admin-only-get-repo-group-shares">Get Repo Group Shares</a></li>
            <li><a href="#admin-only-share-repo-to-user">Share Repo to User</a></li>
            <li><a href="#admin-only-share-repo-to-group">Share Repo to Group</a></li>
            <li><a href="#admin-only-modify-repo-user-share-permission">Modify Repo User Share Permission</a></li>
            <li><a href="#admin-only-modify-repo-group-share-permission">Modify Repo Group Share Permission</a></li>
            <li><a href="#admin-only-delete-repo-user-share">Delete Repo User Share</a></li>
            <li><a href="#admin-only-delete-repo-group-share">Delete Repo Group Share</a></li>
        </ul>
    </li>

    <li>
        <a href="#admin-only-groups">Groups</a>
        <ul>
            <li><a href="#admin-only-get-all-groups">Get all Groups</a></li>
            <li><a href="#admin-only-delete-a-group">Delete a Group</a></li>
            <li><a href="#admin-only-transfer-a-group">Transfer a Group</a></li>
            <li><a href="#admin-only-get-group-libraries">Get Group Libraries</a></li>
            <li><a href="#admin-only-delete-group-library">Delete Group Library</a></li>
            <li><a href="#admin-only-get-group-members">Get Group Members</a></li>
            <li><a href="#admin-only-delete-group-member">Delete Group Member</a></li>
            <li><a href="#admin-only-add-group-member">Add Group Member</a></li>
            <li><a href="#admin-only-update-group-member-role">Update Group Member Role</a></li>
        </ul>
    </li>

    <li>
        <a href="#admin-only-log">Log</a>
        <ul>
            <li><a href="#admin-only-get-login-log">Get Login Log</a></li>
            <li><a href="#admin-only-get-file-audit-log">Get File Audit Log</a></li>
            <li><a href="#admin-only-get-file-update-log">Get File Update Log</a></li>
            <li><a href="#admin-only-get-perm-audit-log">Get Permission Audit Log</a></li>
        </ul>
    </li>

    <li>
        <a href="#admin-only-organization">Organization</a>
        <ul>
            <li><a href="#admin-only-add-organization">Add Organization</a></li>
            <li><a href="#admin-only-add-organization-user">Add Organization User</a></li>
            <li><a href="#admin-only-delete-organization-user">Delete Organization User</a></li>
            <li><a href="#admin-only-modify-organization-user">Modify Organization User</a></li>
        </ul>
    </li>
</ul>
</li>

</ul>
</div>
</p>

# <a id="seafile-web-api"></a>Seafile Web API

## <a id="api-basics"></a>API Basics

All API calls must be authenticated with a valid Seafile API key.

    curl -H 'Authorization: Token 24fd3c026886e3121b2ca630805ed425c272cb96' https://cloud.seafile.com/api2/auth/ping/

The api key can be retrieved by the obtain auth api. See the <a href="#quick-start">Quick Start</a> for details.

For each API, we provide `curl` examples to illustrate the usage. We also provide `python` and `javascript` examples, please refer to https://github.com/haiwen/webapi-examples for details.

## <a id="status-code"></a>Status Code

- 200: OK
- 201: CREATED
- 202: ACCEPTED
- 301: MOVED_PERMANENTLY
- 400: BAD_REQUEST
- 403: FORBIDDEN
- 404: NOT_FOUND
- 409: CONFLICT
- 429: TOO_MANY_REQUESTS
- 440: REPO_PASSWD_REQUIRED
- 441: REPO_PASSWD_MAGIC_REQUIRED
- 500: INTERNAL_SERVER_ERROR
- 520: OPERATION_FAILED

## <a id="quick-start"></a>Quick Start

**ping**

    curl https://cloud.seafile.com/api2/ping/

    "pong"

**obtain auth token**

    curl -d "username=username@example.com&password=123456" https://cloud.seafile.com/api2/auth-token/

    {"token": "24fd3c026886e3121b2ca630805ed425c272cb96"}


you should use `--data-urlencode` if you want to process some special characters properly.

    curl --data-urlencode username=user+name@example.com -d password=123456 https://cloud.seafile.com/api2/auth-token/

    {"token":"265757b0a5aaf5d6b2e266d0c21791121ce6cdec"}

**auth ping**

    curl -H 'Authorization: Token 24fd3c026886e3121b2ca630805ed425c272cb96' https://cloud.seafile.com/api2/auth/ping/

    "pong"

## <a id="account"></a>Account

### <a id="check-account-info"></a>Check Account Info

**GET** https://cloud.seafile.com/api2/account/info/

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/account/info/

**Sample response**

    {
    "usage": 26038531,
    "total": 104857600,
    "email": "user@example.com"
    }

**Errors**

* 403 Invalid token

### <a id="server-info"></a>Get Server Information

**GET** https://cloud.seafile.com/api2/server-info

*Note*:

- No authentication required.
- Added in seafile community edition server `4.0.5` or pro edition server `4.0.3`

**Sample request**

    curl https://cloud.seafile.com/api2/server-info/

**Sample response**

Sample response from a seafile community edition server:

    {
        "version": "4.0.6",
        "features": [
        "seafile-basic",
        ]
    }

Sample response from a seafile pro edition server:

    {
        "version": "4.0.6",
        "features": [
        "seafile-basic",
        "seafile-pro",
        "office-preview",
        "file-search"
        ]
    }

## <a id="starred-files"></a>Starred Files

### <a id="list-starred-files"></a>List starred files

**GET** https://cloud.seafile.com/api2/starredfiles/


**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e6199b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/starredfiles/

**Sample response**

    [
    {
        "repo": "99b758e6-91ab-4265-b705-925367374cf0",
        "mtime": 1355198150,
        "org": -1,
        "path": "/foo/bar.doc",
        "dir": false,
        "size": 0
    },
    {
        "repo": "99b758e6-91ab-4265-b705-925367374cf0",
        "mtime": 1353751237,
        "org": -1,
        "path": "/add_folder-blue.png",
        "dir": false,
        "size": 3170
    }
    ]

### <a id="star-a-file"></a>Star A File

**POST** https://cloud.seafile.com/api2/starredfiles/

**Request parameters**

* repo_id (post)
* p (post)

**Sample request**

    curl -v -d "repo_id=dae8cecc-2359-4d33-aa42-01b7846c4b32&p=/foo.md" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/starredfiles/

**Sample response**

    ...
    < HTTP/1.0 201 CREATED
    < Location: https://cloud.seafile.com/api2/starredfiles/
    ...
    "success"

**Success**

   Response code is 201(Created) and Location header provides url of starred file list.

**Errors**

* 400 `repo_id` or `p` is missing, or `p` is not valid file path(e.g. /foo/bar/).

### <a id="unstar-a-file"></a>Unstar A File

**DELETE** https://cloud.seafile.com/api2/starredfiles/

**Request parameters**

* repo_id
* p

**Sample request**

    curl -X DELETE -v  -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' 'https://cloud.seafile.com/api2/starredfiles/?repo_id=dae8cecc-2359-4d33-aa42-01b7846c4b32&p=/foo.md'

**Sample response**

    ...
    < HTTP/1.0 200 OK
    ...
    "success"

**Success**

   Response code is 200(OK), and a string named "success" is returned.

**Errors**

* 400 `repo_id` or `p` is missing, or `p` is not valid file path(e.g. /foo/bar/).

## <a id="group"></a>Group

### <a id="list-groups"></a>List Groups

**GET** https://cloud.seafile.com/api2/groups/


**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api2/groups/"

**Sample response**

    {
        "replynum": 0,
        "groups": [
            {
                "ctime": 1398134171327948,
                "creator": "user@example.com",
                "msgnum": 0,
                "mtime": 1398231100,
                "id": 1,
                "name": "lian"
            },
            {
                "ctime": 1398236081042441,
                "creator": "user@example.com",
                "msgnum": 0,
                "mtime": 0,
                "id": 2,
                "name": "123"
            }
        ]
    }

### <a id="add-a-group"></a>Add a Group

**POST** https://cloud.seafile.com/api/v2.1/groups/

**Request parameters**

* name (name of new group)

**Sample request**

```
curl -d "name=new_group_name" -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/groups/
```

**Sample response**

```
{
    "name": "new_group_name",
    "owner": "lian@lian.com",
    "created_at": "2015-12-17T10:29:57+0800",
    "admins": ["lian@lian.com"],
    "avatar_url": "https://cloud.seafile.com/media/avatars/groups/default.png",
    "id": 773
}
```

### <a id="get-info-of-a-group"></a>Get Info of a Group

**GET** https://cloud.seafile.com/api/v2.1/groups/772/

**Request parameters**

* avatar_size
* with_repos (0 or 1, if return library info of group. default 0 not return)

**Sample request**

```
curl -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/groups/772/
```

**Sample response**

```
{
    "name": "rename_group_name",
    "owner": "lian@lian.com",
    "created_at": "2015-12-17T10:29:57+0800",
    "admins": ["lian@lian.com"],
    "avatar_url": "https://cloud.seafile.com/media/avatars/groups/default.png",
    "id": 772
}
```

### <a id="rename-a-group"></a>Rename a Group

**PUT** https://cloud.seafile.com/api/v2.1/groups/772/

**Request parameters**

* name (name of new group)

**Sample request**

```
curl -X PUT -d "name=rename_group_name" -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/groups/772/
```

**Sample response**

```
{
    "name": "rename_group_name",
    "owner": "lian@lian.com",
    "created_at": "2015-12-17T10:29:57+0800",
    "admins": ["lian@lian.com"],
    "avatar_url": "https://cloud.seafile.com/media/avatars/groups/default.png",
    "id": 772
}
```

### <a id="transfer-a-group"></a> Transfer a Group

**PUT** https://cloud.seafile.com/api/v2.1/groups/772/

**Request parameters**

* owner (new owner of this group, should be an email.)

**Sample request**

```
curl -X PUT -d "owner=new_owner@new_owner.com" -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/groups/772/
```

**Sample response**

```
{
    "name": "rename_group_name",
    "owner": "new_owner@new_owner.com",
    "created_at": "2015-12-17T10:29:57+0800",
    "admins": ["lian@lian.com", "new_owner@new_owner.com"],
    "avatar_url": "https://cloud.seafile.com/media/avatars/groups/default.png",
    "id": 772
}
```

### <a id="delete-a-group"></a> Delete a Group

**DELETE** https://cloud.seafile.com/api/v2.1/groups/772/

**Sample request**

```
curl -X DELETE -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/groups/772/
```

**Sample response**

```
{"success":true}
```

### <a id="quit-group"></a> Quit Group

**DELETE** https://cloud.seafile.com/api/v2.1/groups/770/members/myself@email.com/

**Sample request**

```
curl -X DELETE -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/groups/770/members/myself@email.com/
```

**Sample response**

```
{"success":true}
```

### <a id="group-member"></a>Group Member

#### <a id="list-group-members"></a>List All Group Members

**GET** https://cloud.seafile.com/api/v2.1/groups/770/members/

**Request parameters**

* avatar_size
* is_admin (`true` or `false`, if ONLY return admin members of group. default `false` return all members)

**Sample request**

```
curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api/v2.1/groups/770/members/"
```

**Sample response**

```
[
    {
        "login_id": "",
        "name": "nickname-of-lian",
        "avatar_url": "https://cloud.seafile.com/media/avatars/default.png",
        "is_admin": true,
        "contact_email": "lian_contact@email.com",
        "email": "lian@lian.com"
    },
    {
        "login_id": "",
        "name": "1",
        "avatar_url": "https://cloud.seafile.com/media/avatars/default.png",
        "is_admin": false,
        "contact_email": "1@1.com",
        "email": "1@1.com"
    }
]
```

#### <a id="add-a-group-member"></a>Add a Group Member

**POST** https://cloud.seafile.com/api/v2.1/groups/770/members/

**Request parameters**

* email

**Sample request**

```
curl -d "email=new-member@email.com" -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/groups/770/members/
```

**Sample response**

```
{
    "login_id": "",
    "name": "new-member",
    "avatar_url": "https://cloud.seafile.com/media/avatars/default.png",
    "is_admin": false,
    "contact_email": "new-member@email.com",
    "email": "new-member@email.com"
}
```

#### <a id="bulk-add-group-members"></a>Bulk Add Group Members

**POST** https://cloud.seafile.com/api/v2.1/groups/770/members/bulk/

**Request parameters**

* emails

**Sample request**

```
curl -d "emails=new-member-1@email.com,new-member-2@email.com,new-member-3@email.com" -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/groups/770/members/bulk/
```

**Sample response**

```
{
    "failed":[
        {
            "error_msg": "Invalid email",
            "email": "new-member-3@email.com"
        },
        {
            "error_msg": "Is already group member",
            "email": "new-member-4@email.com"
        }
    "success":[
        {
            "login_id": "",
            "name": "new-member-1",
            "avatar_url": "https://cloud.seafile.com/media/avatars/default.png",
            "is_admin": false,
            "contact_email": "new-member-1@email.com",
            "email": "new-member-1@email.com"
        },
        {
            "login_id": "",
            "name": "new-member-2",
            "avatar_url": "https://cloud.seafile.com/media/avatars/default.png",
            "is_admin": false,
            "contact_email": "new-member-2@email.com",
            "email": "new-member-2@email.com"
        }
    ]
}

```

#### <a id="get-info-of-a-group-member"></a>Get Info of a Group Member

**GET** https://cloud.seafile.com/api/v2.1/groups/770/members/group-member@email.com/

**Sample request**

```
curl -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/groups/770/members/group-member@email.com/
```

**Request parameters**

* avatar_size

**Sample response**

```
{
    "login_id": "",
    "name": "group-member",
    "avatar_url": "https://cloud.seafile.com/media/avatars/default.png",
    "is_admin": false,
    "contact_email": "group-member@email.com",
    "email": "group-member@email.com"
}
```

#### <a id="set-a-group-member-admin"></a>Set a Group Member Admin

**PUT** https://cloud.seafile.com/api/v2.1/groups/770/members/group-member@email.com/

**Request parameters**

* is_admin=true

**Sample request**

```
curl -X PUT -d "is_admin=true" -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/groups/770/members/group-member@email.com/
```

**Sample response**

```
{
    "login_id": "",
    "name": "group-member",
    "avatar_url": "https://cloud.seafile.com/media/avatars/default.png",
    "is_admin": true,
    "contact_email": "group-member@email.com",
    "email": "group-member@email.com"
}
```

#### <a id="unset-a-group-member-admin"></a>Unset a Group Member Admin

**PUT** https://cloud.seafile.com/api/v2.1/groups/770/members/group-member@email.com/

**Request parameters**

* is_admin=false

**Sample request**

```
curl -X PUT -d "is_admin=false" -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/groups/770/members/group-member@email.com/
```

**Sample response**

```
{
    "login_id": "",
    "name": "group-member",
    "avatar_url": "https://cloud.seafile.com/media/avatars/default.png",
    "is_admin": false,
    "contact_email": "group-member@email.com",
    "email": "group-member@email.com"
}
```

#### <a id="delete-a-group-member"></a> Delete a Group Member

**DELETE** https://cloud.seafile.com/api/v2.1/groups/770/members/group-member@email.com/

**Sample request**

```
curl -X DELETE -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/groups/770/members/group-member@email.com/
```

**Sample response**

```
{"success":true}
```

### <a id="group-message"></a>Group Message

#### <a id="get-group-messages"></a>Get Group Messages

**GET** https://cloud.seafile.com/api2/groups/{group_id}/discussions/

**Request parameters**

* group_id
* page (default 1)
* per_page (default 20)
* avatar_size (default 80)

**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api2/groups/772/discussions/"

**Sample response**

```
{'current_page': 1,
 'msgs': [{'avatar_url': 'https://cloud.seafile.com/media/avatars/default.png',
           'content': u'test',
           'created_at': '2016-07-11T09:18:20+08:00',
           'group_id': 772,
           'id': 1,
           'user_email': u'lian@lian.com',
           'user_login_id': '',
           'user_name': u'name-of-lian'}],
 'page_num': 1}
```

#### <a id="send-a-group-message"></a>Send A Group Message

**POST** https://cloud.seafile.com/api2/groups/{group_id}/discussions/

**Request parameters**

* group_id
* content
* avatar_size (default 80)

**Sample request**

    curl -d "content=this is another test" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api2/groups/772/discussions/"

**Sample response**

```
{'avatar_url': 'https://cloud.seafile.com/media/avatars/default.png',
 'content': u'this is another test',
 'created_at': '2016-07-11T09:27:49+08:00',
 'group_id': 772,
 'id': 3,
 'user_email': u'lian@lian.com',
 'user_login_id': '',
 'user_name': u'name-of-lian'}
```

#### <a id="delete-a-group-message"></a>Delete A Group Message

**DELETE** https://cloud.seafile.com/api2/groups/772/discussions/3/

**Request parameters**

* group_id
* discuss_id

**Sample request**

    curl -v -X DELETE -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api2/groups/772/discussions/3/"

**sample response**

```
...
< http/1.0 204 no content
...
```

**Errors**

* 400 Discussion id not found.
* 403 Permission denied.

## <a id="share"></a>Share

### <a id="share-link"></a>File Share Link

#### <a id="list-all-share-links"></a>List all Share Links

This api will list all folder/file download share links in all libraries created by user.

**GET** https://cloud.seafile.com/api/v2.1/share-links/

**Sample request**

    curl -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' -H 'Accept: application/json; charset=utf-8; indent=4' "https://cloud.seafile.com/api/v2.1/share-links/"

**Sample response**
```
[
    {
        "username": "lian@lian.com",
        "repo_id": "c474a093-19dc-4ddf-b0b0-72b33214ba33",
        "ctime": "2017-04-01T02:35:57+00:00",
        "expire_date": "",
        "token": "6afa667ff2c248378b70",
        "view_cnt": 0,
        "link": "https://cloud.seafile.com/d/6afa667ff2c248378b70/",
        "obj_name": "/",
        "path": "/",
        "is_dir": true,
        "is_expired": false,
        "repo_name": "seacloud.cc.124"
    },
    {
        "username": "lian@lian.com",
        "repo_id": "104f6537-b3a5-4d42-b8b5-8e47e494e4cf",
        "ctime": "2017-04-01T02:35:29+00:00",
        "expire_date": "",
        "token": "0c4eb0cb104a43caaeef",
        "view_cnt": 0,
        "link": "https://cloud.seafile.com/d/0c4eb0cb104a43caaeef/",
        "obj_name": "folder",
        "path": "/folder/",
        "is_dir": true,
        "is_expired": false,
        "repo_name": "for-test-web-api"
    },
    {
        "username": "lian@lian.com",
        "repo_id": "104f6537-b3a5-4d42-b8b5-8e47e494e4cf",
        "ctime": "2017-04-01T02:35:35+00:00",
        "expire_date": "",
        "token": "8c05a00c44db4764b3a5",
        "view_cnt": 0,
        "link": "https://cloud.seafile.com/f/8c05a00c44db4764b3a5/",
        "obj_name": "tmp.md",
        "path": "/tmp.md",
        "is_dir": false,
        "is_expired": false,
        "repo_name": "for-test-web-api"
    }
]
```

**Errors**

* 403 Permission denied.
* 500 Internal Server Error

#### <a id="list-share-links-of-a-library"></a>List Share Links of a Library

This api will list all folder/file download share links in a specific library.

**GET** https://cloud.seafile.com/api/v2.1/share-links/?repo_id={rpeo_id}

**Request parameters**

* repo-id

**Sample request**

    curl -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' -H 'Accept: application/json; charset=utf-8; indent=4' "https://cloud.seafile.com/api/v2.1/share-links/?repo_id=104f6537-b3a5-4d42-b8b5-8e47e494e4cf"

**Sample response**
```
[
    {
        "username": "lian@lian.com",
        "repo_id": "104f6537-b3a5-4d42-b8b5-8e47e494e4cf",
        "ctime": "2017-04-01T02:35:29+00:00",
        "expire_date": "",
        "token": "0c4eb0cb104a43caaeef",
        "view_cnt": 0,
        "link": "https://cloud.seafile.com/d/0c4eb0cb104a43caaeef/",
        "obj_name": "folder",
        "path": "/folder/",
        "is_dir": true,
        "is_expired": false,
        "repo_name": "for-test-web-api"
    },
    {
        "username": "lian@lian.com",
        "repo_id": "104f6537-b3a5-4d42-b8b5-8e47e494e4cf",
        "ctime": "2017-04-01T02:35:35+00:00",
        "expire_date": "",
        "token": "8c05a00c44db4764b3a5",
        "view_cnt": 0,
        "link": "https://cloud.seafile.com/f/8c05a00c44db4764b3a5/",
        "obj_name": "tmp.md",
        "path": "/tmp.md",
        "is_dir": false,
        "is_expired": false,
        "repo_name": "for-test-web-api"
    }
]
```

**Errors**

* 403 Permission denied.
* 404 library not found.
* 500 Internal Server Error

#### <a id="list-share-link-of-a-folder-file"></a>List Share Link of a Folder(File)

This api will list download share link info of a specific folder/file.

**GET** https://cloud.seafile.com/api/v2.1/share-links/?repo_id={rpeo_id}&path={path}

**Request parameters**

* repo-id
* path, could be path of a foler or a file.

**Sample request**

Get folder download share link.

    curl -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' -H 'Accept: application/json; charset=utf-8; indent=4' "https://cloud.seafile.com/api/v2.1/share-links/?repo_id=104f6537-b3a5-4d42-b8b5-8e47e494e4cf&path=/folder/"

**Sample response**
```
[
    {
        "username": "lian@lian.com",
        "repo_id": "104f6537-b3a5-4d42-b8b5-8e47e494e4cf",
        "ctime": "2017-04-01T02:35:29+00:00",
        "expire_date": "",
        "token": "0c4eb0cb104a43caaeef",
        "view_cnt": 0,
        "link": "https://cloud.seafile.com/d/0c4eb0cb104a43caaeef/",
        "obj_name": "folder",
        "path": "/folder/",
        "is_dir": true,
        "is_expired": false,
        "repo_name": "for-test-web-api"
    }
]
```

or a empty list `[]` if this folder has no download share link.

Get file download share link.

    curl -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' -H 'Accept: application/json; charset=utf-8; indent=4' "https://cloud.seafile.com/api/v2.1/share-links/?repo_id=104f6537-b3a5-4d42-b8b5-8e47e494e4cf&path=/tmp.md"

**Sample response**
```
[
    {
        "username": "lian@lian.com",
        "repo_id": "104f6537-b3a5-4d42-b8b5-8e47e494e4cf",
        "ctime": "2017-04-01T02:35:35+00:00",
        "expire_date": "",
        "token": "8c05a00c44db4764b3a5",
        "view_cnt": 0,
        "link": "https://cloud.seafile.com/f/8c05a00c44db4764b3a5/",
        "obj_name": "tmp.md",
        "path": "/tmp.md",
        "is_dir": false,
        "is_expired": false,
        "repo_name": "for-test-web-api"
    }
]
```

or a empty list `[]` if this file has no download share link.

**Errors**

* 403 Permission denied.
* 404 folder/library not found.
* 500 Internal Server Error

#### <a id="create-share-link"></a>Create Share Link

**POST** https://cloud.seafile.com/api/v2.1/share-links/

**Request parameters**

* repo-id
* path (file/folder path)
* password (not necessary)
* expire_date (not necessary)

**Sample request**

Create download link for file

    curl -d "path=/foo.md&repo_id=62ca6cf9-dab6-47e5-badc-bab13d9220ce" -H 'Authorization: Token ef12bf1e66a1aa797a1d6556fdc9ae84f1e9249f' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/share-links/

Create download link for directory with password and expire date

    curl -d "path=/bar/&repo_id=62ca6cf9-dab6-47e5-badc-bab13d9220ce&password=password&expire_date=6" -H 'Authorization: Token ef12bf1e66a1aa797a1d6556fdc9ae84f1e9249f' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/share-links/

**Sample response**

```
{
    "username": "lian@lian.com",
    "view_cnt": 0,
    "ctime": "2016-03-04T04:06:35.477",
    "token": "409f5aa54a",
    "repo_id": "62ca6cf9-dab6-47e5-badc-bab13d9220ce",
    "link": "https://cloud.seafile.com/f/409f5aa54a/",
    "expire_date": null,
    "path": "/foo.md",
    "is_expired": false
}
```

```
{
    "username": "lian@lian.com",
    "view_cnt": 0,
    "ctime": "2016-03-04T04:12:48.959",
    "token": "db1a50e686",
    "repo_id": "62ca6cf9-dab6-47e5-badc-bab13d9220ce",
    "link": "https://cloud.seafile.com/d/db1a50e686/",
    "expire_date": null,
    "path": "/bar/",
    "is_expired": false
}
```

**Errors**

* 400 path/repo_id invalid
* 403 Permission denied.
* 404 file/folder/library not found.
* 500 Internal Server Error

#### <a id="delete-share-link"></a>Delete Share Link

**DELETE** https://cloud.seafile.com/api/v2.1/share-links/{token}/

**Sample request**

    curl -X DELETE -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api/v2.1/share-links/0ae587a7d1/"

**Sample response**

    {"success":true}

#### <a id="send-share-link-email"></a>Send Share Link Email

**POST** https://cloud.seafile.com/api2/send-share-link/

**Request parameters**

* token
* email
* extra_msg (not necessary)

**Sample request**

    curl -d "email=sample@eamil.com,invalid-email&token=4cbd625c5e" -H 'Authorization: Token ef12bf1e66a1aa797a1d6556fdc9ae84f1e9249f' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/send-share-link/

**Sample response**

```
{
    "failed": [
        {
            "email": "invalid-email",
            "error_msg": "email invalid."
        }
    ],
    "success": [
        "sample@eamil.com"
    ]
}
```

**Errors**

* 400 token/repo_id invalid
* 403 Permission denied.
* 403 Sending shared link failed. Email service is not properly configured, please contact administrator.
* 404 token/library not found

#### <a id="list-direntry-in-dir-download-link"></a>List Direntry in Dir Download Link

**GET** https://cloud.seafile.com/api2/d/{token}/dir/

**Request parameters**

* token (upload link token)
* p (sub folder path)
* password (if link is encrypted)

**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api2/d/3af7c46595/dir/?p=/subfolder/"

**Sample response**

    [{"mtime": 1436846750, "type": "dir", "name": "sadof", "id": "1806dbdb700b7bcd49e6275107c7ccf7b3ea1776"}, {"id": "bdb06f6de972c42893fda590ac954988b562429c", "mtime": 1436431020, "type": "file", "name": "test.mdert", "size": 20}]

### <a id="upload-link"></a>Upload Link

#### <a id="list-upload-links"></a>List Upload Links

**GET** https://cloud.seafile.com/api/v2.1/upload-links/

**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api/v2.1/upload-links/"

**Sample response**

    [{"username":"lian@lian.com","repo_id":"62ca6cf9-dab6-47e5-badc-bab13d9220ce","ctime":"2016-03-03T15:26:15.223","token":"9a5d5c8391","link":"https://cloud.seafile.com/u/d/9a5d5c8391/","path":"/"},{"username":"lian@lian.com","repo_id":"78c620ee-2989-4427-8eff-7748f4fbebc0","ctime":"2016-03-04T05:37:17.968","token":"d17d87ea4d","link":"https://cloud.seafile.com/u/d/d17d87ea4d/","path":"/yutong/"}]

#### <a id="create-upload-link"></a>Create Upload Link

**POST** https://cloud.seafile.com/api/v2.1/upload-links/

**Request parameters**

* repo-id
* path (file/folder path)
* password (not necessary)

**Sample request**

Create upload link for directory with password

    curl -d "path=/bar/&repo_id=afc3b694-7d4c-4b8a-86a4-89c9f3261b12&password=password" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/upload-links/

**Sample response**

```
{
    "username": "lian@lian.com",
    "repo_id": "62ca6cf9-dab6-47e5-badc-bab13d9220ce",
    "ctime": "2016-03-04T05:51:34.022",
    "token": "dce40e8594",
    "link": "https://cloud.seafile.com/u/d/dce40e8594/",
    "path": "/bar/"
}
```

**Errors**

* 400 path/repo_id invalid
* 403 Permission denied.
* 500 Internal Server Error

#### <a id="delete-upload-link"></a>Delete Upload Link

**DELETE** https://cloud.seafile.com/api/v2.1/upload-links/{token}/

**Sample request**

    curl -X DELETE -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api/v2.1/upload-links/0ae587a7d1/"

**Sample response**

    {"success":true}

#### <a id="send-upload-link-email"></a>Send Upload Link Email

**POST** https://cloud.seafile.com/api2/send-upload-link/

**Request parameters**

* token
* email
* extra_msg (not necessary)

**Sample request**

    curl -d "email=sample@eamil.com,invalid-email&token=4cbd625c5e" -H 'Authorization: Token ef12bf1e66a1aa797a1d6556fdc9ae84f1e9249f' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/send-upload-link/

**Sample response**

```
{
    "failed": [
        {
            "email": "invalid-email",
            "error_msg": "email invalid."
        }
    ],
    "success": [
        "sample@eamil.com"
    ]
}
```
* 400 token/repo_id invalid
* 403 Permission denied.
* 403 Sending shared link failed. Email service is not properly configured, please contact administrator.
* 404 token/library not found

### <a id="shared-libraries"></a>Shared Libraries

#### <a id="list-user-shared-libraries"></a>List User Shared Libraries

**GET** https://cloud.seafile.com/api2/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/dir/shared_items/?p=/&share_type=user

**Request parameters**

* p, `/` means the **root** folder, which is equivalent to the library.
* share_type, `user`

**Sample request**

    curl -v -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/dir/shared_items/?p=/&share_type=user

**Sample response**

```
[
    {"user_info": {"nickname": "5", "name": "5@1.com"}, "share_type": "user", "permission": "r"},
    {"user_info": {"nickname": "name of 4", "name": "4@1.com"}, "share_type": "user", "permission": "r"}
]
```

**Errors**

* 400 share_type invalid.
* 403 Permission denied.
* 404 Library not found.

#### <a id="list-group-shared-libraries"></a>List Group Shared Libraries

**GET** https://cloud.seafile.com/api2/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/dir/shared_items/?p=/&share_type=group

**Request parameters**

* p, `/` means the **root** folder, which is equivalent to the library.
* share_type, `group`

**Sample request**

    curl -v -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/dir/shared_items/?p=/&share_type=group

**Sample response**

```
[
    {"group_info": {"id": 65, "name": "group"}, "share_type": "group", "permission": "r"},
    {"group_info": {"id": 395, "name": "lsd"}, "share_type": "group", "permission": "rw"}
]
```

**Errors**

* 400 share_type invalid.
* 403 Permission denied.
* 404 Library not found.

#### <a id="list-be-shared-libraries"></a>List Be Shared Libraries

**GET** https://cloud.seafile.com/api2/beshared-repos/

**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api2/beshared-repos/"

**Sample response**

    "[{"user": "user@example.com", "repo_id": "989e3952-9d6f-4427-ab16-4bf9b53212eb", "share_type": "personal", "permission": "rw", "encrypted": false, "repo_desc": "lib shared to imwhatiam", "enc_version": false, "last_modified": 1398218747, "is_virtual": false, "group_id": 0, "repo_name": "lib shared to imwhatiam"}]"

#### <a id="delete-be-shared-library"></a>Delete Be Shared Library

**DELETE** https://cloud.seafile.com/api2/beshared-repos/{repo_id}/?share_type=personal&from=from_user@name.com

**Sample request**

    curl -X DELETE -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/beshared-repos/{repo_id}/?share_type=personal&from=from_user@name.com

**Sample response**

    {"success": true}

**Errors**

* 400 Invalid argument
* 400 Library does not exist

#### <a id="share-a-library-to-user"></a>Share a Library to User

**PUT** https://cloud.seafile.com/api2/repos/{repo_id}/dir/shared_items/?p=/

**Request parameters**

* p, `/` means the **root** folder, which is equivalent to the library.
* share_type, `user`
* username, a email string or a list contains multi emails
* permission, default `r`

**Sample request**

    curl -X PUT -d "share_type=user&username=4@1.com&username=5@1.com&username=invalid@email.com&permission=r" -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/dir/shared_items/?p=/

**Sample response**

```
{
    "failed": [
        {"email": "invalid@email.com", "error_msg": "User invalid@email.com not found."}
    ],
    "success": [
        {"user_info": {"nickname": "name of 4", "name": "4@1.com"}, "share_type": "user", "permission": "r"},
        {"user_info": {"nickname": "5", "name": "5@1.com"}, "share_type": "user", "permission": "r"}
    ]
}
```

**Errors**

* 400 permission invalid.
* 400 share_type invalid.
* 403 Permission denied.
* 404 Library not found.

#### <a id="unshare-a-library-from-user"></a>Unshare a Library from User

**DELETE** https://cloud.seafile.com/api2/repos/{repo_id}/dir/shared_items/?p=/&share_type=user&username=5@1.com

**Request parameters**

* p, `/` means the **root** folder, which is equivalent to the library.
* share_type, `user`
* username, a email string

**Sample request**

    curl -X DELETE -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' -H 'Accept: application/json; charset=utf-8; indent=4' "https://cloud.seafile.com/api2/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/dir/shared_items/?p=/&share_type=user&username=5@1.com"

**Sample response**

```
{"success": true}
```

**Errors**

* 400 share_type invalid.
* 400 email invalid.
* 403 Permission denied.
* 404 Library not found.

#### <a id="update-permission-of-user-shared-library"></a>Update Permission of User Shared Library

**POST** https://cloud.seafile.com/api2/repos/{repo_id}/dir/shared_items/?p=/&share_type=user&username=5@1.com

**Request parameters**

* p, `/` means the **root** folder, which is equivalent to the library.
* share_type, `user`
* username, a email string
* permisson, `r` or `rw`

**Sample request**

    curl -d "permission=r" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; indent=4' "https://cloud.seafile.com/api2/repos/2deffbac-d7be-4ace-b406-efb799083ee9/dir/shared_items/?p=/&share_type=user&username=5@1.com"

**Sample response**

```
{"success": true}
```

**Errors**

* 400 share_type invalid.
* 403 permission invalid.
* 403 Permission denied.
* 404 Library not found.
* 404 Folder not found.

#### <a id="share-a-library-to-group"></a>Share a Library to Group

**PUT** https://cloud.seafile.com/api2/repos/{repo_id}/dir/shared_items/?p=/

**Request parameters**

* p, `/` means the **root** folder, which is equivalent to the library.
* share_type, `group`
* group_id , an integer or a list contains multi integers
* permission, default `r`

**Sample request**

    curl -X PUT -d "share_type=group&group_id=65&group_id=395&group_id=invalid_group_id&group_id=111&permission=rw" -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/dir/shared_items/?p=/

**Sample response**

```
{
    "failed": [],
    "success": [
        {"group_info": {"id": 65, "name": "group"}, "share_type": "group", "permission": "rw"},
        {"group_info": {"id": 395, "name": "lsd"}, "share_type": "group", "permission": "rw"}
    ]
}
```

**Errors**

* 400 permission invalid.
* 400 group_id invalid.
* 400 share_type invalid.
* 403 Permission denied.
* 404 Library not found.

#### <a id="unshare-a-library-from-group"></a>Unshare a Library from Group

**DELETE** https://cloud.seafile.com/api2/repos/{repo_id}/dir/shared_items/?p=/&share_type=group&group=65

**Request parameters**

* p, `/` means the **root** folder, which is equivalent to the library.
* share_type, `group`
* group_id , an integer

**Sample request**

    curl -X DELETE -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' -H 'Accept: application/json; charset=utf-8; indent=4' "https://cloud.seafile.com/api2/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/dir/shared_items/?p=/&share_type=group&group_id=65"

**Sample response**

```
{"success": true}
```

**Errors**

* 400 share_type invalid.
* 400 group_id invalid.
* 403 Permission denied.
* 404 Library not found.

#### <a id="update-permission-of-group-shared-library"></a>Update Permission of Group Shared Library

**POST** https://cloud.seafile.com/api2/repos/{repo_id}/dir/shared_items/?p=/&share_type=group&group_id=65

**Request parameters**

* p, `/` means the **root** folder, which is equivalent to the library.
* share_type, `group`
* group_id , an integer
* permisson, `r` or `rw`

**Sample request**

    curl -d "permission=r" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; indent=4' "https://cloud.seafile.com/api2/repos/2deffbac-d7be-4ace-b406-efb799083ee9/dir/shared_items/?p=/&share_type=group&group_id=65"

**Sample response**

```
{"success": true}
```

**Errors**

* 400 share_type invalid.
* 403 permission invalid.
* 403 Permission denied.
* 404 Library not found.

### <a id="shared-folders"></a>Shared Folders

#### <a id="share-a-folder"></a>Share A Folder

**PUT** https://cloud.seafile.com/api2/repos/{repo-id}/dir/shared_items/?p={path}

* repo-id
* path
* permission, `r` or `rw`
* share_type, `user` or `group`
* username, necessary if share_type is user
* group_id, necessary if share_type is group

**Sample request for share folder to user**

    curl -X PUT -d "username=2@1.com&share_type=user&&perm=r" -H 'Authorization: Token ef12bf1e66a1aa797a1d6556fdc9ae84f1e9249f' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/78c620ee-2989-4427-8eff-7748f4fbebc0/dir/shared_items/?p=/q

**Sample response for share folder to user**

    {"failed": [], "success": [{"user_info": {"nickname": "2", "name": "2@1.com"}, "share_type": "user", "permission": "r"}]}

**Sample request for share folder to group**

    curl -X PUT -d "group_id=772&share_type=group&&perm=rw" -H 'Authorization: Token ef12bf1e66a1aa797a1d6556fdc9ae84f1e9249f' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/78c620ee-2989-4427-8eff-7748f4fbebc0/dir/shared_items/?p=/q

**Sample response for share folder to group**

    {"failed": [], "success": [{"group_info": {"id": 772, "name": "group-2"}, "share_type": "group", "permission": "r"}]}

**Errors**

* 400 share_type/permission/group_id invalid.
* 403 Permission denied.
* 404 Library/Folder/Group not found.
* 500 Failed to get sub repo.

#### <a id="list-shared-folders"></a>List Shared Folders

**GET** https://cloud.seafile.com/api/v2.1/shared-folders/

**Sample request**

    curl -v -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/shared-folders/

**Sample response**

```
[
    {
        "share_permission": "rw",
        "repo_id": "2deffbac-d7be-4ace-b406-efb799083ee9",
        "share_type": "personal",
        "folder_name": "asd",
        "path": "/asd",
        "user_name": "1",
        "contact_email": "contact@email.com",
        "user_email": "1@1.com"
    },
    {
        "share_permission": "r",
        "repo_id": "2deffbac-d7be-4ace-b406-efb799083ee9",
        "share_type": "group",
        "group_name": "test_group",
        "folder_name": "asd",
        "path": "/asd",
        "group_id": 1448
    }
]
```

**Errors**

* 500 Internal Server Error

#### <a id="update-shared-folder-permission"></a>Update Shared Folder Permission

**POST** https://cloud.seafile.com/api2/repos/2deffbac-d7be-4ace-b406-efb799083ee9/dir/shared_items/?p=/asd&share_type=user&username=1@1.com

**Sample request**

    curl -d "permission=r" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/2deffbac-d7be-4ace-b406-efb799083ee9/dir/shared_items/?p=/asd&share_type=user&username=1@1.com

**Sample response**

```
{"success":true}
```

**Errors**

* 400 permission invalid.
* 400 Email invalid.
* 403 Permission denied.
* 404 Library not found.
* 404 Folder not found.
* 500 Internal Server Error

#### <a id="#unshare-a-folder"></a>Unshare A Folder

**POST** https://cloud.seafile.com/api2/repos/2deffbac-d7be-4ace-b406-efb799083ee9/dir/shared_items/?p=/asd&share_type=group&group_id=1448

**Sample request**

    curl -X DELETE -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/2deffbac-d7be-4ace-b406-efb799083ee9/dir/shared_items/?p=/asd&share_type=group&group_id=1448

**Sample response**

```
{"success":true}
```

**Errors**

* 400 Email invalid.
* 403 Permission denied.
* 404 Library not found.
* 404 Folder not found.
* 500 Internal Server Error

## <a id="library"></a>Library

### <a id="get-default-lib"></a>Get Default Library

**GET** https://cloud.seafile.com/api2/default-repo/

**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api2/default-repo/"

**Sample response**

    {
        "repo_id": "691b3e24-d05e-43cd-a9f2-6f32bd6b800e",
        "exists": true
    }

### <a id="create-default-lib"></a>Create Default Library

**POST** https://cloud.seafile.com/api2/default-repo/

**Sample request**

    curl -X POST -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api2/default-repo/"

**Sample response**

    {
        "repo_id": "691b3e24-d05e-43cd-a9f2-6f32bd6b800e",
        "exists": true
    }

### <a id="list-libraries"></a>List Libraries

**GET** https://cloud.seafile.com/api2/repos/

**Sample request**

    curl -H 'Authorization: Token 24fd3c026886e3121b2ca630805ed425c272cb96' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/

**Sample response**

    [
    {
        "permission": "rw",
        "encrypted": false,
        "mtime": 1400054900,
        "owner": "user@mail.com",
        "id": "f158d1dd-cc19-412c-b143-2ac83f352290",
        "size": 0,
        "name": "foo",
        "type": "repo",
        "virtual": false,
        "desc": "new library",
        "root": "0000000000000000000000000000000000000000"
    },
    {
        "permission": "rw",
        "encrypted": false,
        "mtime": 1400054802,
        "owner": "user@mail.com",
        "id": "0536b11a-a5fd-4482-9314-728cb3472f54",
        "size": 0,
        "name": "foo",
        "type": "repo",
        "virtual": false,
        "desc": "new library",
        "root": "0000000000000000000000000000000000000000"
    }
    ]

### <a id="get-library-info"></a>Get Library Info

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/

**Request parameters**

* repo-id

**Sample request**

    curl -G -H 'Authorization: Token 24fd3c026886e3121b2ca630805ed425c272cb96' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/632ab8a8-ecf9-4435-93bf-f495d5bfe975/

**Sample response**

    {
    "encrypted": false,
    "password_need": null,
    "mtime": null,
    "owner": "self",
    "id": "632ab8a8-ecf9-4435-93bf-f495d5bfe975",
    "size": 1356155,
    "name": "org",
    "root": "b5227040de360dd22c5717f9563628fe5510cbce",
    "desc": "org file",
    "type": "repo"
    }

### <a id="get-library-owner"></a>Get Library Owner

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/owner/

**Request parameters**

* repo-id

**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d9b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/owner/

**Sample response**

    {
    "owner": "user@example.com"
    }

**Errors**

* 403 Permission error(only administrator/repo-owner can perform this action).

### <a id="get-library-history"></a>Get Library History

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/history/

**Request parameters**

* repo-id

**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d9b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/history/

**Sample response**

    {"commits": [{"rev_file_size": 0, "rev_file_id": null, "ctime": 1398045167, "creator_name": "imwhatiam123@gmail.com", "creator": "0000000000000000000000000000000000000000", "root_id": "ca2625da6be6e211ddd584615ef3bfaa531e66aa", "rev_renamed_old_path": null, "parent_id": "205c469f0830df09b13024601524058757a43128", "new_merge": false, "repo_id": "691b3e24-d05e-43cd-a9f2-6f32bd6b800e", "desc": "Modified \"api.md\"", "id": "eb62721812e0c3122889b5facde971b353ad176b", "conflict": false, "second_parent_id": null}, {"rev_file_size": 0, "rev_file_id": null, "ctime": 1398045158, "creator_name": "imwhatiam123@gmail.com", "creator": "0000000000000000000000000000000000000000", "root_id": "0b7a31adf4ea8b29ad5a5920420b548da11dd32f", "rev_renamed_old_path": null, "parent_id": "2ba85ee6072efea51a3483843ea7de9b6d1d1eb2", "new_merge": false, "repo_id": "691b3e24-d05e-43cd-a9f2-6f32bd6b800e", "desc": "Added \"api.md\"", "id": "205c469f0830df09b13024601524058757a43128", "conflict": false, "second_parent_id": null}], "page_next": false}

### <a id="get-library-history-limit-days"></a>Get Library History Limit Days

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/history-limit/

**Request parameters**

* repo-id

**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d9b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/history-limit/

**Sample response**

    {
    "keep_days": -1,
    }

**Errors**

* 403 Permission denied.
* 404 Library not found.
* 500 Internal Server Error

### <a id="set-library-history-limit-days"></a>Set Library History Limit Days

**PUT** https://cloud.seafile.com/api2/repos/{repo-id}/history-limit/

**Request parameters**

* repo-id
* keep_days. -1 for keep full history; 0 for do not keep history; positive number for keep a period of limit days.

**Sample request**

    curl -v -X PUT -d "keep_days=4" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/history-limit/

**Sample response**

    {
    "keep_days": 4,
    }

**Errors**

* 400 keep_days invalid.
* 403 Permission denied.
* 404 Library not found.
* 500 Internal Server Error
* 520 Failed to set library history limit.

### <a id="create-library"></a>Create Library

**POST** https://cloud.seafile.com/api2/repos/

**Request parameters**

* name
* desc (defaults to "new repo")
* passwd (needed by encrypt library)

**Sample request**

    curl -v -d "name=foo&desc=new library" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/

**Sample response**

    {
    "encrypted": "",
    "enc_version": 0,
    "repo_id": "f15811fd-5c19-412c-b143-2ac83f352290",
    "magic": "",
    "relay_id": "c5e41170db250ea497075e2911104faf0105b7fb",
    "repo_version": 1,
    "relay_addr": "cloud.seafile.com",
    "token": "c1f3defe9ba408cd7964427ec276843e9d10c23b",
    "relay_port": "10001",
    "random_key": "",
    "email": "user@mail.com",
    "repo_name": "foo"
    }

**Success**

   Response code 200 and newly created library information are returned.

**Errors**

* 400 Library name missing.
* 520 Operation failed.

### <a id="check/create-sub-library"></a>Check/Create Sub Library

check if a dir has a corresponding sub_repo, if it does not have, create one

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/dir/sub_repo/?p=/\&name=sub_lib

**Request parameters**

* repo-id
* p
* name

**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d9b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/dir/sub_repo/?p=/\&name=sub_lib

**Sample response**

    {"sub_repo_id": "c0a3283c-013c-4a7c-8f68-006f06fa6dec"}

**Errors**

* 400 Argument missing
* 500 INTERNAL SERVER ERROR

### <a id="delete-library"></a>Delete Library

**DELETE** https://cloud.seafile.com/api2/repos/{repo-id}/

**Sample request**

    curl -v -X DELETE -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/8f5f2222-72a8-454f-ac40-8397c5a556a8/

**Sample response**

"success"

**Errors**

* 400 Library does not exist.

* 403 Only library owner can perform this operation.

### <a id="rename-library"></a>Rename Library

**POST** https://cloud.seafile.com/api2/repos/{repo-id}/?op=rename

**Sample request**

    curl -d "repo_name=new-repo-name"  -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/8f5f2222-72a8-454f-ac40-8397c5a556a8/op=rename

**Sample response**

"success"

**Errors**

* 404 Library not found.
* 403 You do not have permission to rename this library.
* 500 Unable to rename library

### <a id="transfer-library"></a>Transfer Library

**PUT** https://cloud.seafile.com/api2/repos/{repo-id}/owner/

**Request parameters**

* repo-id
* owner

**Sample request**

    curl -v -X PUT -d "owner=new@owner.com" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d9b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/owner/

**Sample response**

    {
    "success": True
    }

**Errors**

* 440 Email invalid.
* 403 Permission error(only administrator/repo-owner can perform this action).
* 404 Library not found.
* 404 User not found.

### <a id="decrypt-library"></a>Decrypt Library

**POST** https://cloud.seafile.com/api2/repos/{repo-id}/

**Request parameters**

* password

**Sample request**

    curl -v -d "password=123" -H 'Authorization: Token e6a33d61954f219a96b60f635cf02717964e4385' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/0c2465a5-4753-4660-8a22-65abec9ec8d0/

**Sample response**

"success"

**Errors**

* 400 Incorrect password
* 409 Repo is not encrypt
* 500 Internal server error

### <a id="create-public-lib"></a>Create Public Library

**POST** https://cloud.seafile.com/api2/repos/public/

**Request parameters**

* name
* permission, `r` or `rw`, default `r`.
* passwd (optional).

**Sample request**, create an encrypted public repo with `rw` permission

    curl -X POST -d "name=test-public-repo&permission=rw&passwd=password" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d9b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/public/

**Sample response**

```
{
    "owner_nickname": "lian",
    "permission": "rw",
    "encrypted": true,
    "mtime_relative": "<time datetime=\"2016-05-31T12:01:49\" is=\"relative-time\" title=\"Tue, 31 May 2016 12:01:49 +0800\" >1 second ago</time>",
    "mtime": 1464667309,
    "owner": "lian@lian.com",
    "id": "6553fd8b-bf3e-41ad-a481-90c8523d3b4a",
    "size": 0,
    "name": "test-public-repo",
    "desc": "",
    "size_formatted": "0 bytes"
}
```

**Errors**

* 400 Library name is required.
* 400 Invalid permission
* 403 You do not have permission to create library.
* 403 NOT allow to create encrypted library.

### <a id="set-exist-lib-as-public-lib"></a>Set Exist Lib as Public Library

**PUT** https://cloud.seafile.com/api2/shared-repos/{repo-id}/?share_type=public

**Request parameters**

* repo_id
* share_type, must be `public`
* permission, `r` or `rw`.

**Sample request**, create an encrypted public repo with `rw` permission

    curl -X PUT -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d9b477fd' -H 'Accept: application/json; indent=4' 'https://cloud.seafile.com/api2/shared-repos/2deffbac-d7be-4ace-b406-efb799083ee9/?share_type=public&permission=rw'

**Sample response**

```
success
```

**Errors**

* 400 Permission need to be rw or r.
* 403 You do not have permission to share library.
* 500 Failed to share library to public.

### <a id="remove-public-lib"></a>Remove Public Library

**DELETE** https://cloud.seafile.com/api2/shared-repos/{repo-id}/?share_type=public

**Request parameters**

* repo-id
* share_type

**Sample request**

    curl -X DELETE -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d9b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/shared-repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/?share_type=public

**Success**

    "success"

**Errors**

* 400 Share type is required.
* 400 Share type can only be personal or group or public.
* 403 You do not have permission to unshare library.

### <a id="fetch-library-download-info"></a>Fetch library download info

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/download-info/

**Request parameters**

* repo-id

**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d9b477fd' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/download-info/

**Sample response**

    {
    "applet_root": "https://localhost:13420",
    "relay_addr": "localhost",
    "token": "46acc4d9ca3d6a5c7102ef379f82ecc1edc629e1",
    "repo_id": "dae8cecc-2359-4d33-aa42-01b7846c4b32",
    "relay_port": "10002",
    "encrypted": "",
    "repo_name": "test",
    "relay_id": "8e4b13b49ca79f35732d9f44a0804940d985627c",
    "email": "user@example.com"
    }

### <a id="search-files-in-libraries"></a>Search Files in Libraries

**GET** https://cloud.seafile.com/api2/search/

**Request parameters**

* `q`, keyword for searching.

* `per_page`, optional.

* `search_repo`, `all` or a *repo_id*, (`all` for searching in all libraries), optional.

* `search_ftypes`, `all` or `custom`, (`all` for searching all file types, `custom` for only searching the specific file types you defined in `ftype` and `input_fexts`).

* `ftype`, must be in (`Text`, `Document`, `Image`, `Video`, `Audio`, `PDF`, `Markdown`).

* `input_fexts`, file extensions manually specific.

**Sample request**

    curl -H 'Authorization: Token e44e3c81b70b07e3a5f580db8ffcbb886f8ee06d' -H 'Accept: application/json; charset=utf-8; indent=4' "https://cloud.seafile.com/api2/search/?q=seafile&search_repo=all&search_ftypes=custom&ftype=Document&input_fexts=md,png"

**Sample response**
```
{
    "has_more": false,
    "total": 2,
    "results": [
        {
            "repo_id": "36eeafad-6acd-4c69-a8b7-b3f27af56dc0",
            "name": "seafile-tutorial.doc",
            "oid": "b88ab96740ef53249b9d21fb3fa28050842266ba",
            "last_modified": 1490861602,
            "fullpath": "/office file/office-2/seafile-tutorial.doc",
            "repo_name": "123com",
            "is_dir": false,
            "size": 300544
        },
        {
            "repo_id": "97d4006f-c1e1-4b75-b31c-6ef89d580844",
            "name": "seafile-tutorial.doc",
            "oid": "b88ab96740ef53249b9d21fb3fa28050842266ba",
            "last_modified": 1490861602,
            "fullpath": "/seafile-tutorial.doc",
            "repo_name": "123com",
            "is_dir": false,
            "size": 300544
        }
    ]
}
```

**Errors**

* 404 Search not supported.
* 400 Missing argument q.

### <a id="get-library-download-links"></a>Get Library Download Links

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/download-shared-links/

**Request parameters**

* repo-id

**Sample request**

    curl -H 'Authorization: Token 24fd3c026886e3121b2ca630805ed425c272cb96' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/632ab8a8-ecf9-4435-93bf-f495d5bfe975/download-shared-links/

**Sample response**

    [
        {
            "view_count": 0,
            "name": "/",
            "share_type": "d",
            "creator_name": "lian",
            "create_by": "lian@lian.com",
            "token": "105f108fb6",
            "create_time": "2016-01-18T15:03:10+0800",
            "path": "/",
            "size": ""
        },
        {
            "view_count": 3,
            "name": "1.md",
            "share_type": "f",
            "creator_name": "lian",
            "create_by": "lian@lian.com",
            "token": "a626012c1b",
            "create_time": "2016-01-19T11:27:43+0800",
            "path": "/1.md",
            "size": "4"
        }
    ]

**Errors**

* 403 Permission denied.
* 404 Library not found.

#### <a id="get-library-upload-links"></a>Get Library Upload Links

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/upload-shared-links/

**Request parameters**

* repo-id

**Sample request**

    curl -H 'Authorization: Token 24fd3c026886e3121b2ca630805ed425c272cb96' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/632ab8a8-ecf9-4435-93bf-f495d5bfe975/upload-shared-links/

**Sample response**

    [
        {
            "view_count": 3,
            "name": "/",
            "creator_name": "lian",
            "create_by": "lian@lian.com",
            "token": "43340efca5",
            "create_time": "2016-01-18T15:03:12+0800",
            "path": "/"
        },
        {
            "view_count": 8,
            "name": "a&b",
            "creator_name": "lian",
            "create_by": "lian@lian.com",
            "token": "f1e49d445a",
            "create_time": "2016-01-18T15:03:18+0800",
            "path": "/a&b/"
        }
    ]

**Errors**

* 403 Permission denied.
* 404 Library not found.

#### <a id="delete-library-download-link"></a>Delete Library Download Link

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/download-shared-links/{token}/

**Request parameters**

* repo-id
* token

**Sample request**

    curl -X DELETE -H 'Authorization: Token 24fd3c026886e3121b2ca630805ed425c272cb96' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/632ab8a8-ecf9-4435-93bf-f495d5bfe975/download-shared-links/105f108fb6/

**Sample response**

    {"success": true}

**Errors**

* 403 Permission denied.
* 404 Library not found.
* 404 Link not found.

#### <a id="delete-library-upload-link"></a>Delete Library Upload Link

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/upload-shared-links/{token}/

**Request parameters**

* repo-id
* token

**Sample request**

    curl -X DELETE -H 'Authorization: Token 24fd3c026886e3121b2ca630805ed425c272cb96' -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/632ab8a8-ecf9-4435-93bf-f495d5bfe975/upload-shared-links/f1e49d445a/

**Sample response**

    {"success": true}

**Errors**

* 403 Permission denied.
* 404 Library not found.
* 404 Link not found.

## <a id="file"></a>File

### <a id="view-file-through-owa"></a>View File Through Owa

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/owa-file/?path=/foo.docx

**Request parameters**

* repo-id
* path

**Sample request**

    curl  -v  -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' 'https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/owa-file/?path=/foo.docx'

**Sample response**

```
{
    "access_token": "7decacff-6e55-4856-9734-01aaab26ef45",
    "action_url": "http://off1.off.com/wv/wordviewerframe.aspx?WOPIsrc=http%3A%2F%2F192.168.1.124%3A8000%2Fapi2%2Fwopi%2Ffiles%2F2b0750085925fa85238e5f64cfd13ed6f1076bfd%2F",
    "access_token_ttl": 1456906784000
}
```

**After get response**

In order to instantiate the Office Online applications, a host must create an HTML page that will host an iframe element within it pointing to a particular WOPI action URL. And then use a form element and POST the `access_token` and `access_token_ttl` values to the Office Online.

For more info, you can see [this official docs](http://wopi.readthedocs.org/en/latest/hostpage.html).

**Errors**

* 400 path invalid.
* 403 permission denied.
* 403 Library encrypted.
* 403 Office Web App feature not enabled.
* 403 Office Web App feature only supported in professional edition.
* 404 File/Library not found.
* 500 Internal Server Error

### <a id="download-file"></a>Download File

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/file/?p=/foo

**Request parameters**

* repo-id
* p
* reuse (optional): Set `reuse` to `1` if you want the generated download link can be accessed more than once in one hour.

**Sample request**

    curl  -v  -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' 'https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/file/?p=/foo.c&reuse=1'

**Sample response**

    "https://cloud.seafile.com:8082/files/adee6094/foo.c"

**Errors**

* 400 Path is missing
* 404 File not found
* 520 Operation failed.

### <a id="get-file-detail"></a>Get File Detail

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/file/detail/?p=/foo.c

* repo-id
* p

**Sample request**

    curl -H 'Authorization: Token f2210dacd3606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/file/detail/?p=/foo.c

**Sample response**

    {
    "id": "013d3d38fed38b3e8e26b21bb3463eab6831194f",
    "mtime": 1398148877,
    "type": "file",
    "name": "foo.py",
    "size": 22
    }

**Errors**

* 400 Path is missing
* 520 Operation failed.

### <a id="get-file-history"></a>Get File History

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/file/history/?p=/foo.c

**Request parameters**

* repo-id
* p

**Sample request**

    curl -H 'Authorization: Token f2210dacd3606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/file/history/?p=/foo.c

**Sample response**

    {
    "commits":
        [
            {
            "rev_file_size": 0,
            "repo_id": "a582d3bc-bcf5-421e-9125-741fa56d18d4",
            "ctime": 1398149763,
            "creator_name": "user@example.com",
            "creator": "0000000000000000000000000000000000000000",
            "root_id": "b64d413d9894c9206beac3faf9c2a0d75b4a8ebf",
            "rev_renamed_old_path": null,
            "parent_id": "8e546762e1657ab22dad83e9cb1e5ea31a767c9a",
            "new_merge": false,
            "version": 1,
            "conflict": false,
            "desc": "Added \"foo.c\"",
            "id": "9464f7499bfa7363d563282361339eaf96a93318",
            "rev_file_id": "0000000000000000000000000000000000000000",
            "second_parent_id": null
            },
            {
            "rev_file_size": 0,
            "repo_id": "a582d3bc-bcf5-421e-9125-741fa56d18d4",
            "ctime": 1398146059,
            "creator_name": "user@example.com",
            "creator": "0000000000000000000000000000000000000000",
            "root_id": "572413414257c76039897e00aeb35f819471206b",
            "rev_renamed_old_path": null,
            "parent_id": "f977bdb0ebb205645c3b42216c2817e511c3f68f",
            "new_merge": false,
            "version": 1,
            "conflict": false,
            "desc": "Added \"foo.c\"",
            "id": "a1ec20709675f4dc8db825cdbca296be245d189b",
            "rev_file_id": "0000000000000000000000000000000000000000",
            "second_parent_id": null
            }
        ]
    }

**Errors**

* 400 Path is missing
* 404 File not found

### <a id="restore-file-from-history"></a>Restore File From History

**POST** http://192.168.1.124:8000/api/v2.1/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/file/?p=/1.md

**Request parameters**

* repo_id
* p
* operation
* commit_id

**Sample request**

    curl -d "operation=revert&commit_id=7ed3ccdc7559d1afddb95bc050230e3d54bbffef" -H "Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a" -H 'Accept: application/json; indent=4' "http://192.168.1.124:8000/api/v2.1/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/file/?p=/1.md"

**Sample response**
```
{
    "success": true
}
```

**Errors**

* 400 commit_id invalid.
* 403 Permission denied.
* 403 File is locked
* 500 Internal Server Error
* 500 Check file lock error

### <a id="download-file-revision"></a>Download File From a Revision

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/file/revision/?p=/foo.c&commit_id=a1ec20709675f4dc8db825cdbca296be245d189b

**Request parameters**

* repo-id
* p
* commit_id

**Sample request**

    curl -H 'Authorization: Token f2210dacd3606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/file/revision/?p=/foo.c\&commit_id=a1ec20709675f4dc8db825cdbca296be245d189b

**Sample response**

    "https://cloud.seafile.com:8082/files/adee6094/foo.c"

**Errors**

* 400 Path is missing
* 404 Revision not found

### <a id="create-file"></a>Create File

**POST** https://cloud.seafile.com/api2/repos/{repo-id}/file/?p=/foo.c

**Request parameters**

* repo-id
* p
* operation

**Sample request**

    curl -v -d "operation=create" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/file/?p=/foo.c

**Sample response**

    ...
    < HTTP/1.1 201 CREATED
    ...
    "success"

**Success**

   Response code is 201, and a string `"success"` is returned.

**Errors**

* 403 FORBIDDEN, You do not have permission to move file
* 520 OPERATION FAILED, fail to create file

### <a id="rename-file"></a>Rename File

**POST** https://cloud.seafile.com/api2/repos/{repo-id}/file/?p=/foo.c

**Request parameters**

* repo-id
* p
* operation=rename
* newname

**Sample request**

    curl -v -d "operation=rename&newname=newfoo.c" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/file/?p=/foo.c

**Sample response**

    ...
    < HTTP/1.1 301 MOVED PERMANENTLY
    ...
    "success"

**Success**

   Response code is 301, and a string `"success"` is returned.

**Errors**

* 400 BAD REQUEST, Path is missing or invalid(e.g. p=/) or newname is missing(newname too long)
* 403 FORBIDDEN, You do not have permission to rename file
* 404 NOT FOUND, repo not found
* 409 CONFLICT, the newname is the same to the old
* 520 OPERATION FAILED, fail to rename file

### <a id="lock-file"></a>Lock File

**PUT** https://cloud.seafile.com/api2/repos/{repo-id}/file/

**Request parameters**

* repo-id
* p
* operation

**Sample request**

    curl -v -X PUT -d "operation=lock&p=/foo.c" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/file/

**Sample response**

    ...
    < HTTP/1.0 200 OK
    ...
    "success"

**Success**

   Response code is 200, and a string `"success"` is returned.

**Errors**

* 400 BAD REQUEST, Path is missing or invalid(e.g. p=/)
* 403 FORBIDDEN, You do not have permission to lock file
* 404 NOT FOUND, repo not found
* 520 OPERATION FAILED, fail to lock file

### <a id="unlock-file"></a>Unlock File

**PUT** https://cloud.seafile.com/api2/repos/{repo-id}/file/

**Request parameters**

* repo-id
* p
* operation

**Sample request**

    curl -v -X PUT -d "operation=unlock&p=/foo.c" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/file/

**Sample response**

    ...
    < HTTP/1.0 200 OK
    ...
    "success"

**Success**

   Response code is 200, and a string `"success"` is returned.

**Errors**

* 400 BAD REQUEST, Path is missing or invalid(e.g. p=/)
* 403 FORBIDDEN, You do not have permission to lock file
* 404 NOT FOUND, repo not found
* 520 OPERATION FAILED, fail to unlock file

### <a id="move-file"></a>Move File

**POST** https://cloud.seafile.com/api2/repos/{repo-id}/file/?p=/foo.c

**Request parameters**

* repo-id
* p
* operation
* dst_repo
* dst_dir

**Sample request**

    curl -v -d "operation=move&dst_repo=affc837f-7fdd-4e91-b88a-32caf99897f2&dst_dir=/" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/file/?p=/foo.c

**Sample response**

    ...
    < HTTP/1.1 301 MOVED PERMANENTLY
    ...
    "success"

**Success**

   Response code is 301, and a string `"success"` is returned.

**Errors**

* 400 BAD REQUEST, Path is missing or invalid(e.g. p=/)
* 403 FORBIDDEN, You do not have permission to move file
* 404 NOT FOUND, repo not found
* 500 INTERNAL SERVER ERROR

### <a id="copy-file"></a>Copy File

**POST** https://cloud.seafile.com/api2/repos/{repo-id}/file/?p=/foo.c

**Request parameters**

* repo-id
* p
* operation
* dst_repo
* dst_dir

**Sample request**

    curl -v -d "dst_repo=73ddb2b8-dda8-471b-b7a7-ca742b07483c&dst_dir=/&file_names=foo.c" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' https://cloud.seafile.com/api2/repos/c7436518-5f46-4296-97db-2fcba4c8c8db/file/?p=/foo.c

**Sample response**

    ...
    < HTTP/1.1 200 OK
    ...
    "success"

**Success**

   Response code is 200, and a string `"success"` is returned.

**Errors**

* 400 BAD REQUEST, Path is missing or invalid(e.g. p=/)
* 403 FORBIDDEN, You do not have permission to copy file
* 500 INTERNAL SERVER ERROR

### <a id="revert-file"></a>Revert File

**PUT** https://cloud.seafile.com/api2/repos/{repo_id}/file/revert/

**Request parameters**

* repo_id
* p
* commit_id

**Sample request**

    curl -v -X PUT -d "commit_id=a1ec20709675f4dc8db825cdbca296be245d189b&p=/foo.c" -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/8f5f2222-72a8-454f-ac40-8397c5a556a8/file/revert/

**Sample response**

    ...
    < HTTP/1.0 200 OK
    ...

    {"ret": 0}

**Success**

    Response code 200(OK) is returned.

**Errors**

* 400 Path is missing

### <a id="delete-file"></a>Delete File

**DELETE** https://cloud.seafile.com/api2/repos/{repo-id}/file/?p=/foo

**Request parameters**

* repo-id
* p

**Sample request**

    curl -X DELETE -v  -H 'Authorization: Token f2210dacd3606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/file/?p=/foo.c

**Sample response**

    ...
    < HTTP/1.0 200 OK
    ...
    "success"

**Errors**

* 400 Path is missing
* 520 Operation failed.

**Note**

   This can also be used to delete directory.

### <a id="upload-file"></a>Upload File

#### <a id="get-upload-link"></a>Get Upload Link

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/upload-link/?p=/upload-dir

**Request parameters**

* repo-id
* p (use '/' as default)

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" https://cloud.seafile.com/api2/repos/99b758e6-91ab-4265-b705-925367374cf0/upload-link/

**Sample response**

    "http://cloud.seafile.com:8082/upload-api/73c5d117-3bcf-48a0-aa2a-3f48d5274ae3"

**Errors**

    403 Permission denied.
    500 Run out of quota

#### <a id="upload-file-1"></a>Upload File

After getting the upload link, POST to this link for uploading files.

**POST** http://cloud.seafile.com:8082/upload-api/73c5d117-3bcf-48a0-aa2a-3f48d5274ae3

**Request parameters**

* file: local file path.
* parent_dir : path in your Seafile repo that you want to upload local file to.
* relative_path: sub path of "parent_dir", if this sub path does not exist, Seafile will create it recursively.
* ret-json: returns a json array including file info if set to `1`.

> NOTE:
> 1. `parent_dir` must endswith `/`
> 1. `relative_path` must NOT startswith `/`

**Sample request**

upload file to `/path-in-seafile-repo/`:

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -F file=@local-folder/test.txt -F parent_dir=/path-in-seafile-repo/ http://cloud.seafile.com:8082/upload-api/73c5d117-3bcf-48a0-aa2a-3f48d5274ae3

**Sample response for no `ret-json` parameter**

    "adc83b19e793491b1c6ea0fd8b46cd9f32e592fc"

upload file to `/path-in-seafile-repo/sub_path_1/sub_path_2/`, Seafile will create `sub_path_1/sub_path_2/` recursively if it does not exist:

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -F file=@local-folder/test.txt -F file=@1.jpg -F parent_dir=/path-in-seafile-repo/ -F relative_path=sub_path_1/sub_path_2/ http://cloud.seafile.com:8082/upload-api/73c5d117-3bcf-48a0-aa2a-3f48d5274ae3?ret-json=1

**Sample response for with `?ret-json=1` parameter**
```
[
    {
        "name": "test.txt",
        "id": "4ccd37916552e2943314027931edd0b45240be7c",
        "size": 2987
    },
    {
        "name": "1.jpg",
        "id": "12e07dd00c124fa7ea3b645ff9fe183f73eab2a1",
        "size": 1699246
    }
]
```

**Note**

- New uploaded file name will be 'test(1).text' if a file with name 'test.txt' already exists in parent directory

- For python client uploading, see <https://github.com/haiwen/webapi-examples/blob/master/python/upload-file.py>, or it can be done much more easily with elegant [python requests library](http://docs.python-requests.org/en/latest/), see <https://github.com/haiwen/webapi-examples/blob/master/python/upload-file2.py>

**Errors**

    400 Bad request
    440 Invalid filename
    500 Internal server error

### <a id="update-file"></a>Update file

#### <a id="get-update-link"></a>Get Update Link

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/update-link/?p=/update-dir

**Request parameters**

* repo-id
* p (use '/' as default)

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" https://cloud.seafile.com/api2/repos/99b758e6-91ab-4265-b705-925367374cf0/update-link/

**Sample response**

    "http://cloud.seafile.com:8082/update-api/e69e5ee7-9329-4f42-bf1b-12879bd72c28"

**Errors**

    403 Permission denied.
    500 Run out of quota

#### <a id="update-file-1"></a>Update File

After getting the update link, POST to this link for updating files.

**POST** http://cloud.seafile.com:8082/update-api/e69e5ee7-9329-4f42-bf1b-12879bd72c28

**Request parameters**

* target_file

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -F file=@test.txt -F filename=test.txt -F target_file=/test.txt http://cloud.seafile.com:8082/update-api/e69e5ee7-9329-4f42-bf1b-12879bd72c28

**Returns**

The id of the updated file

**Sample response**

    "adc83b19e793491b1c6ea0fd8b46cd9f32e592fc"

**Errors**

- 400 Bad request
- 440 Invalid filename
- 500 Internal server error

### <a id="get-upload-blks-link"></a>Get Upload Blocks Link

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/upload-blks-link/

**Request parameters**

* repo-id

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" https://cloud.seafile.com/api2/repos/99b758e6-91ab-4265-b705-925367374cf0/upload-blks-link/

**Sample response**

    "https://cloud.seafile.com/seafhttp/upload-blks-api/569213db-7297-457a-907d-e2259a277c05"

**Errors**

- 403 Can not access repo
- 520 above quota

### <a id="get-update-blks-link"></a>Get Update Blocks Link

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/update-blks-link/

**Request parameters**

* repo-id

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" https://cloud.seafile.com/api2/repos/99b758e6-91ab-4265-b705-925367374cf0/update-blks-link/

**Sample response**

    "https://cloud.seafile.com/seafhttp/update-blks-api/402c6d48-fe52-4592-97dd-85f462f03d66"

**Errors**

- 403 Can not access repo
- 520 above quota

## <a id="directory">Directory

### <a id="list-directory-entries"></a>List Directory Entries

**GET** https://cloud.seafile.com/api2/repos/{repo-id}/dir/

* repo-id
* p (optional): The path to a directory. If `p` is missing, then defaults to '/' which is the top directory.
* oid (optional): The object id of the directory. The object id is the checksum of the directory contents.
* t (optional): If set `t` argument as `f`, will only return file entries, and `d` for only dir entries.
* recursive (optional): If set `t` argument as `d` **AND** `recursive` argument as `1`, return all dir entries recursively

**Sample request**

request file/dir list of a folder.

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d9b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/repos/99b758e6-91ab-4265-b705-925367374cf0/dir/?p=/foo

**Sample response**

   If oid is the same as the current oid of the directory, returns `"uptodate"` , else returns

    [
    {
        "id": "0000000000000000000000000000000000000000",
        "type": "file",
        "name": "test1.c",
        "size": 0
    },
    {
        "id": "e4fe14c8cda2206bb9606907cf4fca6b30221cf9",
        "type": "dir",
        "name": "test_dir"
    }
    ]

**Sample request**

request recursive dir list of a folder.

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d9b477fd" -H 'Accept: application/json; indent=4' 'https://cloud.seafile.com/api2/repos/99b758e6-91ab-4265-b705-925367374cf0/dir/?t=d&recursive=1'

**Sample response**

```
[{'id': u'5e307101cad46398fb5fe52d9177836f73c4bae8',
  'mtime': 1471490386,
  'name': u'123',
  'parent_dir': u'/video',
  'permission': u'rw',
  'type': 'dir'},
 {'id': u'0000000000000000000000000000000000000000',
  'mtime': 1471490391,
  'name': u'123-2',
  'parent_dir': u'/video',
  'permission': u'rw',
  'type': 'dir'},
 {'id': u'0000000000000000000000000000000000000000',
  'mtime': 1471490379,
  'name': u'456',
  'parent_dir': u'/video/123',
  'permission': u'rw',
  'type': 'dir'},
 {'id': u'0000000000000000000000000000000000000000',
  'mtime': 1471490386,
  'name': u'456-2',
  'parent_dir': u'/video/123',
  'permission': u'rw',
  'type': 'dir'},
 {'id': u'd8f5f80fbd89bf5634dcf9e21b569c487541d34e',
  'mtime': 1471490391,
  'name': u'video',
  'parent_dir': '/',
  'permission': u'rw',
  'type': 'dir'}
]
```

**Errors**

* 404 The path is not exist.
* 440 Repo is encrypted, and password is not provided.
* 520 Operation failed..

### <a id="create-new-directory"></a>Create New Directory

**POST** https://cloud.seafile.com/api2/repos/{repo-id}/dir/

* repo-id
* p
* operation=mkdir (post)

**Sample request**

    curl -d  "operation=mkdir" -v  -H 'Authorization: Tokacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/dir/?p=/foo

**Sample response**

    ...
    < HTTP/1.0 201 CREATED
    < Location: https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/dir/?p=/foo
    ...

    "success"

**Success**

   Response code 201(Created) is returned, and Location header provides the url of created directory.

**Errors**

* 400 Path is missing or invalid(e.g. p=/)
* 520 Operation failed.

**Notes**

   Newly created directory will be renamed if the name is duplicated.

### <a id="rename-directory"></a>Rename Directory

**POST** https://cloud.seafile.com/api2/repos/{repo-id}/dir/?p=/foo

**Parameters**

* repo-id
* p (path)
* operation=rename
* newname (the new name of the directory)

**Sample request**

    curl -d  "operation=rename&newname=pinkfloyd_newfolder" -v  -H 'Authorization: Tokacd9c6ccb8133606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/dir/?p=/foo

**Success**

   Response code 200 if everything is ok

**Errors**

* 403 if You do not have permission to rename a folder
* 400 if newname is not given
* 520 if Failed to rename directory (generic problem)

**Notes**

   If the new name is the same of the old name no operation will be done.

### <a id="delete-directory"></a>Delete Directory

**DELETE** https://cloud.seafile.com/api2/repos/{repo-id}/dir/

* repo-id
* p

**Sample request**

    curl -X DELETE -v  -H 'Authorization: Token f2210dacd3606d94ff8e61d99b477fd' -H 'Accept: application/json; charset=utf-8; indent=4' https://cloud.seafile.com/api2/repos/dae8cecc-2359-4d33-aa42-01b7846c4b32/dir/?p=/foo

**Sample response**

    ...
    < HTTP/1.0 200 OK
    ...
    "success"

**Success**

   Response code is 200(OK), and a string `"success"` is returned.

**Errors**

* 400 Path is missing or invalid(e.g. p=/)
* 520 Operation failed.

**Note**

   This can also be used to delete file.

### <a id="download-directory"></a>Download Directory

Perform the following two steps to download directory

##### <a id="download-directory-get-tast-toke"></a>Get Task Token

**GET** https://cloud.seafile.com/api/v2.1/repos/{repo-id}/zip-task/?parent_dir={parent_dir}&dirents={dir}

* repo-id
* parent_dir
* dirents

**Sample request**

    curl -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' -H 'Accept: application/json; charset=utf-8; indent=4' "https://cloud.seafile.com/api/v2.1/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/zip-task/?parent_dir=/&dirents=my_dir_name"

**Sample response**

    {
        "zip_token": "b2272645-35ee-44ce-8f68-07c022107015"
    }

**Errors**

* 400 parent_dir/dirents invalid.
* 400 Unable to download directory: size is too large.
* 404 Library/Folder not found.
* 403 Permission denied.
* 500 Internal Server Error

### <a id="revert-directory"></a>Revert Directory

**PUT** http://192.168.1.124:8000/api2/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/dir/revert/

* repo_id
* p
* commit_id

**Sample request**

    curl -X PUT -d "p=/456&commit_id=b1a33768517f65ac7d618ff078dd27855374c7e0" -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' -H 'Accept: application/json; charset=utf-8; indent=4' "http://192.168.1.124:8000/api2/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/dir/revert/"

**Sample response**
```
{
    "success": true
}
```

**Errors**

* 400 path invalid.
* 400 commit_id invalid.
* 404 Library/Folder not found.
* 403 Permission denied.
* 500 Internal Server Error

##### <a id="download-directory-query-task-progress"></a>Query Task Progress

Use the token returned from previous request to check if task progress finished.

**GET** https://cloud.seafile.com/api/v2.1/query-zip-progress/?token={token}

* token

**Sample request**

    curl -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' -H 'Accept: application/json; charset=utf-8; indent=4' "https://cloud.seafile.com/api/v2.1/query-zip-progress/?token=b2272645-35ee-44ce-8f68-07c022107015"

**Sample response**

If `zipped` is equal to `total`, means task finished.

    {
        "zipped":2,
        "total":2
    }

**Errors**

* 400 token invalid.
* 500 Internal Server Error

After the task finished, you can manually generate directory download url with the `zip_token`:

    FILE_SERVER_ROOT/zip/{zip_token}

For example, `https://cloud.seafile.com/seafhttp/zip/b2272645-35ee-44ce-8f68-07c022107015` is the final url here.

## <a id="multiple-files-directories">Multiple Files / Directories

### <a id="multiple-files-directories-copy"></a>Copy

**POST** https://cloud.seafile.com/api2/repos/{repo_id}/fileops/copy/

**Request parameters**

* p: source folder path, defaults to `"/"`
* file_names: list of file/folder names to copy. Multiple file/folder names can be seperated by `:`.
* dst_repo: the destination repo id
* dst_dir: the destination folder in `dst_repo`

**Sample request**

    curl -d "dst_repo=73ddb2b8-dda8-471b-b7a7-ca742b07483c&dst_dir=/&file_names=foo.c:bar.c:dir1:dir2" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' https://cloud.seafile.com/api2/repos/c7436518-5f46-4296-97db-2fcba4c8c8db/fileops/copy/

**Sample response**

    "success"

**Errors**

* 400 missing argument
* 403 You do not have permission to copy file
* 404 repo not found
* 502 failed to copy file

### <a id="multiple-files-directories-move"></a>Move

**POST** https://cloud.seafile.com/api2/repos/{repo_id}/fileops/move/

**Request parameters**

* p: source folder path, defaults to `"/"`
* file_names: list of file/folder names to move. Multiple file/folder names can be seperated by `:`.
* dst_repo: the destination repo id
* dst_dir: the destination folder in `dst_repo`

**Sample request**

    curl -d "dst_repo=73ddb2b8-dda8-471b-b7a7-ca742b07483c&dst_dir=/&file_names=foo.c:bar.c:dir1:dir2" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' https://cloud.seafile.com/api2/repos/c7436518-5f46-4296-97db-2fcba4c8c8db/fileops/move/

**Sample response**

    "success"

**Errors**

* 400 missing argument
* 403 You do not have permission to move file
* 404 repo not found
* 502 failed to move file

### <a id="multiple-files-directories-delete"></a>Delete

**POST** https://cloud.seafile.com/api2/repos/{repo_id}/fileops/delete/

**Request parameters**

* p: source folder path, defaults to `"/"`
* file_names: list of file/folder names to delete. Multiple file/folder names can be seperated by `:`.

**Sample request**

    curl -d "file_names=foo.c:bar.c:dir1:dir2" -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' https://cloud.seafile.com/api2/repos/c7436518-5f46-4296-97db-2fcba4c8c8db/fileops/delete/

**Sample response**

    "success"

**Errors**

* 400 missing argument
* 403 You do not have permission to delete file
* 404 repo not found
* 502 failed to delete file

### <a id="multiple-files-directories-download"></a>Download

Perform the following two steps to download multiple files and directories.

##### <a id="multiple-files-directories-get-tast-toke"></a>Get Task Token

**GET** https://cloud.seafile.com/api/v2.1/repos/{repo-id}/zip-task/?parent_dir={parent_dir}&dirents={dir,file}

* repo-id
* parent_dir
* dirents

**Sample request**

    curl -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' -H 'Accept: application/json; charset=utf-8; indent=4' "https://cloud.seafile.com/api/v2.1/repos/7460f7ac-a0ff-4585-8906-bb5a57d2e118/zip-task/?parent_dir=/&dirents=my_dir_name&dirents=my_file_name"

**Sample response**

    {
        "zip_token": "b2272645-35ee-44ce-8f68-07c022107015"
    }

**Errors**

* 400 parent_dir/dirents invalid.
* 400 Unable to download directory: size is too large.
* 404 Library/Folder not found.
* 403 Permission denied.
* 500 Internal Server Error

##### <a id="multiple-files-directories-query-task-progress"></a>Query Task Progress

Use the token returned from previous request to check if task progress finished.

**GET** https://cloud.seafile.com/api/v2.1/query-zip-progress/?token={token}

* token

**Sample request**

    curl -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' -H 'Accept: application/json; charset=utf-8; indent=4' "https://cloud.seafile.com/api/v2.1/query-zip-progress/?token=b2272645-35ee-44ce-8f68-07c022107015"

**Sample response**

If `zipped` is equal to `total`, means task finished.

    {
        "zipped":2,
        "total":2
    }

**Errors**

* 400 token invalid.
* 500 Internal Server Error

After the task finished, you can manually generate directory download url with the `zip_token`:

    FILE_SERVER_ROOT/zip/{zip_token}

For example, `https://cloud.seafile.com/seafhttp/zip/b2272645-35ee-44ce-8f68-07c022107015` is the final url here.

## <a id="avatar"></a>Avatar

### <a id="get-user-avatar"></a>Get User Avatar

**GET** https://cloud.seafile.com/api2/avatars/user/{user}/resized/{size}/

**Request parameters**

* user
* size

**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api2/avatars/user/user@example.com/resized/80/"

**Sample response**

    {
        "url": "http://127.0.0.1:8000/media/avatars/default.png",
        "is_default": true,
        "mtime": 0
    }

### <a id="get-group-avatar"></a>Get Group Avatar

**GET** https://cloud.seafile.com/api2/avatars/group/{group_id}/resized/{size}/

**Request parameters**

* group_id
* size

**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api2/avatars/group/1/resized/80/"

**Sample response**

    {
        "url": "http://127.0.0.1:8000/media/avatars/groups/default.png",
        "is_default": true,
        "mtime": 0
    }

## <a id="devices"></a>Devices

### <a id="get-user-devices"></a>Get User Devices

**GET** https://cloud.seafile.com/api2/devices/

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/devices/

**Sample response**

```
[
    {
        "synced_repos": [
            {
                "repo_id": "47945b31-dedb-4b92-a048-32bf825595ce",
                "sync_time": 1458008928,
                "repo_name": "wopi"
            },
            {
                "repo_id": "78c620ee-2989-4427-8eff-7748f4fbebc0",
                "sync_time": 1457943466,
                "repo_name": "lib-of-lian"
            }
        ],
        "last_accessed": "2016-03-15T10:28:48+08:00",
        "device_name": "lian",
        "platform_version": "",
        "platform": "linux",
        "user": "lian@lian.com",
        "key": "99abe1a7cc7d614db0bfa19db81e42ef675abe4f",
        "client_version": "5.0.0",
        "last_login_ip": "192.168.1.16",
        "device_id": "be10980211752515053bf9036a13139375de0cc8"
    },
    {
        "last_accessed": "2016-03-15T13:59:51+08:00",
        "device_name": "PLK-AL10",
        "platform_version": "5.0.2",
        "platform": "android",
        "user": "lian@lian.com",
        "key": "067051c94163ed193f2131d48c61882daa7cb238",
        "client_version": "2.0.3",
        "last_login_ip": "192.168.1.208",
        "device_id": "4a0d62c1f27b3b74"
    }
]
```

**Errors**

* 401 UNAUTHORIZED

### <a id="unlink-user-device"></a>Unlink User Device

**DELETE** https://cloud.seafile.com/api2/devices/

**Request parameters**

* platform
* device_id

**Sample request**

    curl -X DELETE -d "platform=linux&device_id=be10980211752515053bf9036a13139375de0cc8" -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/devices/

**Sample response**

    {"success": true}

**Errors**

* 400 platform invalid
* 400 device_id invalid
* 500 Internal Server Error

## <a id="get-file-activities"></a>Get File Activities

**GET** https://cloud.seafile.com/api2/events/

**Request parameters**

this api will only return first 15 records of activities. if want get more, pass `start` parameter

* start (default 0)
* size (size of user avatar, default 36)

**Sample request**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api2/events/"

**Sample response**

```
{'events': [{'author': u'lian@lian.com',
             'avatar': '<img src="/media/avatars/default.png" width="36" height="36" class="avatar" />',
             'avatar_url': 'https://cloud.seafile.com/media/avatars/default.png',
             'date': '2016-05-06',
             'etype': u'repo-delete',
             'name': u'lian',
             'nick': u'lian',
             'repo_id': u'13e2ae06-8927-465b-8f57-319b3a7cfbdd',
             'repo_name': u'2',
             'time': 1462552942,
             'time_relative': u'<time datetime="2016-05-06T16:42:22.967104" is="relative-time" title="Fri, 6 May 2016 16:42:22 +0800" >19 hours ago</time>'},
            {'author': u'lian@lian.com',
             'avatar': '<img src="/media/avatars/default.png" width="36" height="36" class="avatar" />',
             'avatar_url': 'https://cloud.seafile.com/media/avatars/default.png',
             'commit_id': u'1be92d40a1b526863bbf39e8abdae7d317a1195f',
             'converted_cmmt_desc': u'Modified "<a href="/convert_cmmt_desc_link/?repo_id=47945b31-dedb-4b92-a048-32bf825595ce&cmmt_id=1be92d40a1b526863bbf39e8abdae7d317a1195f&nm=excel-view.xlsx" class="normal">excel-view.xlsx</a>"',
             'date': '2016-04-25',
             'desc': u'Modified "excel-view.xlsx"',
             'etype': u'repo-update',
             'more_files': False,
             'name': u'lian',
             'nick': u'lian',
             'repo_encrypted': False,
             'repo_id': u'47945b31-dedb-4b92-a048-32bf825595ce',
             'repo_name': u'wopi',
             'time': 1461569125,
             'time_relative': u'<time datetime="2016-04-25T15:25:25" is="relative-time" title="Mon, 25 Apr 2016 15:25:25 +0800" >11 days ago</time>'}
             ...
             ],
 'more': True,
 'more_offset': 15}
 ```

**Sample request for more activities**

    curl -H 'Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd' "https://cloud.seafile.com/api2/events/?start=15"

**Sample response for more activities**

```
{'events': [{'author': u'lian@lian.com',
             'avatar': '<img src="/media/avatars/default.png" width="36" height="36" class="avatar" />',
             'avatar_url': 'https://cloud.seafile.com/media/avatars/default.png',
             'date': '2016-05-06',
             'etype': u'repo-delete',
             'name': u'lian',
             'nick': u'lian',
             'repo_id': u'13e2ae06-8927-465b-8f57-319b3a7cfbdd',
             'repo_name': u'2',
             'time': 1462552942,
             'time_relative': u'<time datetime="2016-05-06T16:42:22.967104" is="relative-time" title="Fri, 6 May 2016 16:42:22 +0800" >19 hours ago</time>'},
            {'author': u'lian@lian.com',
             'avatar': '<img src="/media/avatars/default.png" width="36" height="36" class="avatar" />',
             'avatar_url': 'https://cloud.seafile.com/media/avatars/default.png',
             'commit_id': u'1be92d40a1b526863bbf39e8abdae7d317a1195f',
             'converted_cmmt_desc': u'Modified "<a href="/convert_cmmt_desc_link/?repo_id=47945b31-dedb-4b92-a048-32bf825595ce&cmmt_id=1be92d40a1b526863bbf39e8abdae7d317a1195f&nm=excel-view.xlsx" class="normal">excel-view.xlsx</a>"',
             'date': '2016-04-25',
             'desc': u'Modified "excel-view.xlsx"',
             'etype': u'repo-update',
             'more_files': False,
             'name': u'lian',
             'nick': u'lian',
             'repo_encrypted': False,
             'repo_id': u'47945b31-dedb-4b92-a048-32bf825595ce',
             'repo_name': u'wopi',
             'time': 1461569125,
             'time_relative': u'<time datetime="2016-04-25T15:25:25" is="relative-time" title="Mon, 25 Apr 2016 15:25:25 +0800" >11 days ago</time>'}
             ...
             ],
 'more': True,
 'more_offset': 30}
 ```

## <a id="get-thumbnail-image"></a>Get Thumbnail Image

**GET** https://cloud.seafile.com/api2/repos/{repo_id}/thumbnail/

**Request parameters**

* repo_id
* p
* size

**Sample request**

    curl -H 'Authorization: Token 40f9a510a0629430865dc199a3880898ad2e48fc' https://cloud.seafile.com/api2/repos/fbead5d0-4817-4446-92f3-7ac8e6a8e5f5/thumbnail/?p=/5.jpg\&size=123 > thumbnail.png

### <a id="search-user"></a>Search User

**GET** https://cloud.seafile.com/api2/search-user/?q=foo

**Request parameters**

* q

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/search-user/?q=foo

**Sample response**

```
[
    {'avatar_url': 'https://cloud.seafile.com/media/avatars/default.png',
      'contact_email': u'foo@foo.com',
      'email': u'foo@foo.com',
      'name': 'foo'},
    {'avatar_url': 'https://cloud.seafile.com/media/avatars/default.png',
     'contact_email': u'foo-bar@foo-bar.com',
     'email': u'foo-bar@foo-bar.com',
     'name': 'foo-bar'}
]
```

**Errors**

* 400 Argument missing.
* 403 Guest user can not use global address book.


Note: The following APIs are only available since Seafile v5.1.

# <a id="admin-only"></a>Admin Only

## <a id="admin-only-account"></a>Account

### <a id="admin-only-list-accounts"></a>List Accounts

**GET** https://cloud.seafile.com/api2/accounts/

**Request parameters**

* start (default to 0)
* limit (default to 100)
* scope (default None, accepted values: 'LDAP' or 'DB' or 'LDAPImport')

To retrieve all users, just set both `start` and `limit` to `-1`.

If scope parameter is passed then accounts will be searched inside the specific scope, otherwise it will be used the old approach: first LDAP and, if no account is found, DB.

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/accounts/

**Sample response**

    [
    {
        "email": "foo@foo.com"
    },
    {
        "email": "bar@bar.com"
    }
    ]

**Errors**

* 403 Permission error, only administrator can perform this action

### <a id="admin-only-get-account"></a>Get Account Info

**GET** https://cloud.seafile.com/api2/accounts/{email}/

**Request parameters**

**Sample request**

    curl -v -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/accounts/user@mail.com/

**Sample response**

    {
    "is_staff": false,
    "is_active": true,
    "id": 2,
    "create_time": 1356061187741686,
    "usage": 651463187,
    "total": 107374182400,
    "email": "user@mail.com"
    }

**Errors**

* 403 Permission error, only administrator can perform this action

### <a id="admin-only-create-account"></a>Create Account

**PUT** https://cloud.seafile.com/api2/accounts/{email}/

**Request parameters**

* password
* is_staff (defaults to False)
* is_active (defaults to True)

**Sample request**

    curl -v -X PUT -d "password=123456" -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/accounts/newaccount@gmail.com/

**Sample response**

    ...
    < HTTP/1.0 201 CREATED
    < Location: https://cloud.seafile.com/api2/accounts/newaccount@gmail.com/
    ...

    "success"

**Success**

    Response code 201(Created) is returned and the Location header provides shared link.

**Errors**

* 403 Permission error, only administrator can perform this action

### <a id="admin-only-update-account"></a>Update Account

**PUT** https://cloud.seafile.com/api2/accounts/{email}/

**Request parameters**

At least one of followings:

* password
* is_staff
* is_active
* name
* note
* storage

**Sample request**

    curl -v -X PUT -d "password=654321&is_staff=true&storage=1073741824" -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/accounts/user@mail.com/

**Sample response**

    ...
    < HTTP/1.0 200 OK
    ...

    "success"

**Success**

    Response code 200(OK) is returned.

**Errors**

* 400 Bad Request, keyword password is required
* 403 Permission error, only administrator can perform this action

### <a id="admin-only-migrate-account"></a>Migrate Account

**POST** https://cloud.seafile.com/api2/accounts/{email}/

**Request parameters**

* op
* to_user this user must exist

**Sample request**

    curl -v -d "op=migrate&to_user=user2@mail.com" -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/accounts/user@mail.com/

**Sample response**

    ...
    < HTTP/1.0 200 OK
    ...

    "success"

**Success**

    Response code 200(OK) is returned.

**Errors**

* 400 Bad Request, arguments are missing or invalid
* 403 Permission error, only administrator can perform this action

### <a id="admin-only-delete-account"></a>Delete Account

**DELETE** https://cloud.seafile.com/api2/accounts/{email}/


**Sample request**

    curl -v -X DELETE -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/accounts/newaccount@gmail.com/

**Sample response**

    "success"

**Errors**

* 403 Permission error, only administrator can perform this action

## <a id="admin-only-devices"></a>Devices

### <a id="admin-only-get-desktop-devices"></a>Get Desktop Devices

Get first page (50 records per page) of desktop devices.

**GET** https://cloud.seafile.com/api/v2.1/admin/devices/?platform=desktop&page=1&per_page=50

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/devices/?platform=desktop&page=1&per_page=50

**Sample response**

```
[
    {'has_next_page': False},
    [
        {
            'last_accessed': '2016-04-11T18:24:29+08:00',
            'last_login_ip': u'192.168.1.210',
            'platform': u'linux',
            'user': u'1@1.com',
            'client_version': u'2.0.4',
            'device_name': u'PLK-AL10',
            'device_id': u'4a0d62c1f27b3b74'
        }
    ]
]
```

**Errors**

* 403 Permission error, only administrator can perform this action

### <a id="admin-only-get-mobile-devices"></a>Get Mobile Devices

Get first page (50 records per page) of mobile devices.

**GET** https://cloud.seafile.com/api/v2.1/admin/devices/?platform=mobile&page=1&per_page=50

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/devices/?platform=mobile&page=1&per_page=50

**Sample response**

```
[
    {'has_next_page': False},
    [
        {
            'last_accessed': '2016-04-11T18:24:29+08:00',
            'last_login_ip': u'192.168.1.210',
            'platform': u'ios',
            'user': u'1@1.com',
            'client_version': u'2.0.4',
            'device_name': u'PLK-AL10',
            'device_id': u'4a0d62c1f27b3b74'
        }
    ]
]
```

**Errors**

* 403 Permission error, only administrator can perform this action

### <a id="admin-only-unlink-user-device"></a>Unlink User Device

**DELETE** https://cloud.seafile.com/api/v2.1/admin/devices/

**Request parameters**

* platform
* device_id
* user

**Sample request**

    curl -X DELETE -d "platform=linux&device_id=be10980211752515053bf9036a13139375de0cc8&user=1@1.com" -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/devices/

**Sample response**

    {"success": true}

**Errors**

* 400 platform invalid
* 400 device_id invalid
* 400 user invalid
* 500 Internal Server Error

### <a id="admin-only-get-device-errors"></a>Get Device Errors

This api is only supported in pro edition.

**GET** https://cloud.seafile.com/api/v2.1/admin/device-errors/

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/device-errors/

**Sample response**

```
[
    {
        'repo_id': u'47945b31-dedb-4b92-a048-32bf825595ce',
        'device_ip': u'192.168.1.124',
        'error_time': '2016-04-13T17:49:11+08:00',
        'device_name': u'lian-ubuntu-1404-64',
        'email': u'1@1.com',
        'client_version': u'5.0.6',
        'error_msg': u'No permission.',
        'repo_name': u'wopi'
    }
]
```

**Errors**

* 403 Feature disabled.
* 500 Internal Server Error

### <a id="admin-only-clean-device-errors"></a>Clean Device Errors

This api is only supported in pro edition.

**DELETE** https://cloud.seafile.com/api/v2.1/admin/device-errors/

**Sample request**

    curl -X DELETE -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/device-errors/

**Sample response**

```
{"success":true}
```

**Errors**

* 403 Feature disabled.
* 500 Internal Server Error

## <a id="admin-only-default-library"></a>Default Library

### <a id="admin-only-get-user-default-library"></a>Get User Default Library

Available for Seafile v6.0.9+

**GET** https://cloud.seafile.com/api/v2.1/admin/default-library/{user_email}

**Sample request**

    curl -H 'Authorization: Token 024692f8411a656baa2cc2d5ed4cd46177b3b3d0' "https://cloud.seafile.com/api/v2.1/admin/default-library/?user_email=foo@foo.com"

**Sample response**

```
{
    "repo_id":"9e58655f-d2a2-4df9-baa2-5ca50698ad98",
    "exists":true,
    "user_email":"lian@lian.com"
}
```

**Errors**

* 400 user_email invalid.
* 404 User not found.
* 403 Permission error, only administrator can perform this action.
* 500 Internal Server Error

### <a id="admin-only-create-user-default-library"></a>Create User Default Library

Available for Seafile v6.0.9+

**POST** https://cloud.seafile.com/api/v2.1/admin/default-library/

**Sample request**

    curl -d "user_email=foo@foo.com" -H 'Authorization: Token 024692f8411a656baa2cc2d5ed4cd46177b3b3d0' "https://cloud.seafile.com/api/v2.1/admin/default-library/"

**Sample response**

```
{
    "repo_id":"9e58655f-d2a2-4df9-baa2-5ca50698ad98",
    "exists":true,
    "user_email":"lian@lian.com"
}
```

**Errors**

* 400 user_email invalid.
* 403 Permission error, only administrator can perform this action.
* 403 Permission error, user can not create library.
* 404 User not found.
* 500 Internal Server Error

## <a id="admin-only-libraries"></a>Libraries

### <a id="admin-only-get-all-libraries"></a>Get all Libraries

Available for Seafile v6.0.0+

**GET** https://cloud.seafile.com/api/v2.1/admin/libraries/?page=1&per_page=100

Get first page (100 records per page) of libraries.

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/libraries/?page=1&per_page=100

**Sample response**

```
{
    "page_info": {
        "current_page": 1,
        "has_next_page": true
    },
    "repos": [
        {
            "name": null,
            "encrypted": false,
            "file_count": 0,
            "owner": "lian@lian.com",
            "size_formatted": "0 bytes",
            "id": "04df5005-1dfc-4e30-ae55-95ed6559583f",
            "size": 0
        },
        {
            "name": "My Library",
            "encrypted": false,
            "file_count": 161,
            "owner": "lian@lian.com",
            "size_formatted": "25.4 MB",
            "id": "2deffbac-d7be-4ace-b406-efb799083ee9",
            "size": 26617460
        }
        ...
    ]
}
```

**Errors**

* 403 Permission error, only administrator can perform this action

### <a id="admin-only-search-library-by-name"></a>Search Library by Name

Available for Seafile v6.0.0+

**GET** https://cloud.seafile.com/api/v2.1/admin/libraries/?name=file

**Request parameters**

* name

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/libraries/?name=file

**Sample response**
```
{
    "owner": "",
    "repos": [
        {
            "name": "file-preview",
            "encrypted": false,
            "file_count": 25,
            "owner": "lian@lian.com",
            "size_formatted": "10.9 MB",
            "id": "6ce1383b-ed1c-45c7-ab31-a13b64471e64",
            "size": 11437897
        }
    ],
    "name": "file"
}
```

**Errors**

* 403 Permission error, only administrator can perform this action


### <a id="admin-only-search-library-by-owner"></a>Search Library by Owner

Available for Seafile v6.0.0+

**GET** https://cloud.seafile.com/api/v2.1/admin/libraries/?owner=lian@lian.com

**Request parameters**

* owner

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/libraries/?owner=lian@lian.com

**Sample response**
```
{
    "owner": "lian@lian.com",
    "repos": [
        {
            "name": "lib-of-lian",
            "encrypted": false,
            "file_count": 0,
            "owner": "lian@lian.com",
            "size_formatted": "16.5 KB",
            "id": "78c620ee-2989-4427-8eff-7748f4fbebc0",
            "size": 16883
        },
        {
            "name": "encrypted",
            "encrypted": true,
            "file_count": 0,
            "owner": "lian@lian.com",
            "size_formatted": "18.1 MB",
            "id": "47695bb8-3364-4274-939d-3c5a0df9710c",
            "size": 18997225
        },
        ...
    ],
    "name": ""
}
```

**Errors**

* 403 Permission error, only administrator can perform this action

### <a id="admin-only-delete-a-library"></a>Delete a Library

Available for Seafile v6.0.0+

**DELETE** https://cloud.seafile.com/api/v2.1/admin/libraries/{repo_id}/

**Sample request**

    curl -X DELETE -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/admin/libraries/ee3b2d19-1a06-47f0-bbfa-554cab3bdedc/

**Sample response**

```
{"success":true}
```

**Errors**

* 403 Permission error, only administrator can perform this action


### <a id="admin-only-transfer-a-library"></a>Transfer a Library

Available for Seafile v6.0.0+

**PUT** https://cloud.seafile.com/api/v2.1/admin/libraries/{repo_id}/

**Sample request**

    curl -X PUT -d "owner=1@1.com" -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/admin/libraries/ee3b2d19-1a06-47f0-bbfa-554cab3bdedc/

**Sample response**

```
{
    "name": "test-repo",
    "encrypted":false,
    "file_count":0,
    "owner":"1@1.com",
    "size_formatted":"0 bytes",
    "id":"ee3b2d19-1a06-47f0-bbfa-554cab3bdedc",
    "size":0
}
```

**Errors**

* 400 owner invalid.
* 403 Permission error, only administrator can perform this action
* 404 User not found.
* 404 Library not found.
* 500 Internal Server Error

### <a id="admin-only-get-library-dirents"></a>Get Library Dirents

**GET** https://cloud.seafile.com/api/v2.1/admin/libraries/{repo_id}/dirents/?parent_dir={parent_dir}

* repo-id
* parent_dir

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/libraries/104f6537-b3a5-4d42-b8b5-8e47e494e4cf/dirents/?parent_dir=/asd

**Sample response**

```
{
    "repo_id": "c474a093-19dc-4ddf-b0b0-72b33214ba33",
    "dirent_list": [
        {
            "file_size": "",
            "last_update": "2016-12-19T03:35:14+00:00",
            "is_file": false,
            "obj_name": "book"
        },
        {
            "file_size": "",
            "last_update": "2016-10-12T07:43:32+00:00",
            "is_file": false,
            "obj_name": "image"
        },
        {
            "file_size": "47.0 KB",
            "last_update": "2017-02-13T02:41:05+00:00",
            "is_file": true,
            "obj_name": "123.md"
        }
    ],
    "is_system_library": false,
    "repo_name": "seacloud.cc.124"
}
```

**Errors**

* 400 parent_dir invalid.
* 403 Feature disabled.
* 403 Permission error, only administrator can perform this action
* 404 Library not found.
* 404 Folder not found.
* 500 Internal Server Error

## <a id="admin-only-shares"></a>Shares

### <a id="admin-only-get-repo-user-shares"></a>Get Repo User Shares

Available for Seafile v6.0.1+

**GET** https://cloud.seafile.com/api/v2.1/admin/shares/?repo_id={repo_id)&share_type={share_type}

**Request parameters**

* repo_id
* share_type

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' 'https://cloud.seafile.com/api/v2.1/admin/shares/?repo_id=ddd42241-e003-425d-960e-0f9f7144866f&share_type=user'

**Sample response**

```
[
    {
        "repo_id": "ddd42241-e003-425d-960e-0f9f7144866f",
        "share_type": "user",
        "permission": "r",
        "path": "/",
        "user_name": "name of user 2",
        "user_email": "2@2.com"
    }
]
```

**Errors**

* 400 repo_id invalid.
* 400 share_type invalid.
* 403 Permission denied.
* 404 Library not found.
* 404 Folder not found.
* 500 Internal Server Error

### <a id="admin-only-get-repo-group-shares"></a>Get Repo Group Shares

Available for Seafile v6.0.1+

**GET** https://cloud.seafile.com/api/v2.1/admin/shares/?repo_id={repo_id)&share_type={share_type}

**Request parameters**

* repo_id
* share_type

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' 'https://cloud.seafile.com/api/v2.1/admin/shares/?repo_id=ddd42241-e003-425d-960e-0f9f7144866f&share_type=group'

**Sample response**

```
[
    {
        "repo_id": "ddd42241-e003-425d-960e-0f9f7144866f",
        "share_type": "group",
        "permission": "rw",
        "group_name": "group-of-lian-2",
        "path": "/",
        "group_id": 2
    }
]
```

**Errors**

* 400 repo_id invalid.
* 400 share_type invalid.
* 403 Permission denied.
* 404 Library not found.
* 404 Folder not found.
* 500 Internal Server Error

### <a id="admin-only-share-repo-to-user"></a>Share Repo to User

Available for Seafile v6.0.1+

**POST** https://cloud.seafile.com/api/v2.1/admin/shares/

**Request parameters**

* repo_id
* share_type
* share_to (user email)
* permission

**Sample request**

    curl -d "repo_id=ddd42241-e003-425d-960e-0f9f7144866f&share_type=user&permission=r&share_to=1@1.com&share_to=invalid@email.com" -H "Authorization: Token 9c845638b855e549c07ff81be2a0471aa52810d7" -H 'Accept: application/json; indent=4' 'https://cloud.seafile.com/api/v2.1/admin/shares/'

**Sample response**

```
{
    "failed": [
        {
            "error_msg": "User invalid@email.com not found.",
            "user_email": "invalid@email.com"
        }
    ],
    "success": [
        {
            "repo_id": "ddd42241-e003-425d-960e-0f9f7144866f",
            "share_type": "user",
            "permission": "r",
            "path": "/",
            "user_name": "name of user 1",
            "user_email": "1@1.com"
        }
    ]
}
```

**Errors**

* 400 repo_id invalid.
* 400 share_type invalid.
* 403 Permission denied.
* 404 Library not found.
* 404 Folder not found.
* 500 Internal Server Error

### <a id="admin-only-share-repo-to-group"></a>Share Repo to Group

Available for Seafile v6.0.1+

**POST** https://cloud.seafile.com/api/v2.1/admin/shares/

**Request parameters**

* repo_id
* share_type
* share_to (group_id)
* permission

**Sample request**

    curl -d "repo_id=ddd42241-e003-425d-960e-0f9f7144866f&share_type=group&permission=r&share_to=1&share_to=1232" -H "Authorization: Token 9c845638b855e549c07ff81be2a0471aa52810d7" -H 'Accept: application/json; indent=4' 'https://cloud.seafile.com/api/v2.1/admin/shares/'

**Sample response**

```
{
    "failed": [
        {
            "group_id": 1232,
            "error_msg": "Group %s not found"
        }
    ],
    "success": [
        {
            "repo_id": "ddd42241-e003-425d-960e-0f9f7144866f",
            "share_type": "group",
            "permission": "r",
            "group_name": "group-of-lian",
            "path": "/",
            "group_id": 1
        }
    ]
}
```

**Errors**

* 400 repo_id invalid.
* 400 share_type invalid.
* 403 Permission denied.
* 404 Library not found.
* 404 Folder not found.
* 500 Internal Server Error

### <a id="admin-only-modify-repo-user-share-permission"></a>Modify Repo User Share Permission

Available for Seafile v6.0.1+

**PUT** https://cloud.seafile.com/api/v2.1/admin/shares/

**Request parameters**

* repo_id
* share_type
* share_to (user email)
* permission

**Sample request**

    curl -X PUT -d "repo_id=ddd42241-e003-425d-960e-0f9f7144866f&share_type=user&permission=rw&share_to=1@1.com" -H "Authorization: Token 9c845638b855e549c07ff81be2a0471aa52810d7" -H 'Accept: application/json; indent=4' 'https://cloud.seafile.com/api/v2.1/admin/shares/'

**Sample response**

```
{
    "repo_id": "ddd42241-e003-425d-960e-0f9f7144866f",
    "share_type": "user",
    "permission": "rw",
    "path": "/",
    "user_name": "name of user 1",
    "user_email": "1@1.com"
}
```

**Errors**

* 400 repo_id invalid.
* 400 share_type invalid.
* 403 Permission denied.
* 404 Library not found.
* 404 Folder not found.
* 500 Internal Server Error

### <a id="admin-only-modify-repo-group-share-permission"></a>Modify Repo Group Share Permission

Available for Seafile v6.0.1+

**PUT** https://cloud.seafile.com/api/v2.1/admin/shares/

**Request parameters**

* repo_id
* share_type
* share_to (group_id)
* permission

**Sample request**

    curl -X PUT -d "repo_id=ddd42241-e003-425d-960e-0f9f7144866f&share_type=group&permission=rw&share_to=1" -H "Authorization: Token 9c845638b855e549c07ff81be2a0471aa52810d7" -H 'Accept: application/json; indent=4' 'https://cloud.seafile.com/api/v2.1/admin/shares/'

**Sample response**

```
{
    "repo_id": "ddd42241-e003-425d-960e-0f9f7144866f",
    "share_type": "group",
    "permission": "rw",
    "group_name": "group-of-lian",
    "path": "/",
    "group_id": 1
}
```

**Errors**

* 400 repo_id invalid.
* 400 share_type invalid.
* 403 Permission denied.
* 404 Library not found.
* 404 Folder not found.
* 500 Internal Server Error

### <a id="admin-only-delete-repo-user-share"></a>Delete Repo User Share

Available for Seafile v6.0.1+

**DELETE** https://cloud.seafile.com/api/v2.1/admin/shares/

**Request parameters**

* repo_id
* share_type
* share_to (user email)

**Sample request**

    curl -X DELETE -d "repo_id=ddd42241-e003-425d-960e-0f9f7144866f&share_type=user&share_to=1@1.com" -H "Authorization: Token 9c845638b855e549c07ff81be2a0471aa52810d7" -H 'Accept: application/json; indent=4' 'https://cloud.seafile.com/api/v2.1/admin/shares/'

**Sample response**

```
{
    "success": true
}
```

**Errors**

* 400 repo_id invalid.
* 400 share_type invalid.
* 403 Permission denied.
* 404 Library not found.
* 404 Folder not found.
* 500 Internal Server Error

### <a id="admin-only-delete-repo-group-share"></a>Delete Repo Group Share

Available for Seafile v6.0.1+

**DELETE** https://cloud.seafile.com/api/v2.1/admin/shares/

**Request parameters**

* repo_id
* share_type
* share_to (group id)

**Sample request**

    curl -X DELETE -d "repo_id=ddd42241-e003-425d-960e-0f9f7144866f&share_type=group&share_to=1" -H "Authorization: Token 9c845638b855e549c07ff81be2a0471aa52810d7" -H 'Accept: application/json; indent=4' 'https://cloud.seafile.com/api/v2.1/admin/shares/'

**Sample response**

```
{
    "success": true
}
```

**Errors**

* 400 repo_id invalid.
* 400 share_type invalid.
* 403 Permission denied.
* 404 Library not found.
* 404 Folder not found.
* 500 Internal Server Error

## <a id="admin-only-groups"></a>Groups

### <a id="admin-only-get-all-groups"></a>Get all groups

Available for Seafile v6.0.0+

**GET** https://cloud.seafile.com/api/v2.1/admin/groups/?page=1&per_page=100

Get first page (100 records per page) of groups.

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/groups/?page=1&per_page=100

**Sample response**

```
{
    "page_info": {
        "current_page": 1,
        "has_next_page": true
    },
    "groups": [
        {
            "owner": "test@test.com",
            "created_at": "2016-08-01T16:58:14+08:00",
            "id": 1476,
            "name": "test_group"
        },
        {
            "owner": "1@1.com",
            "created_at": "2016-08-02T16:48:14+08:00",
            "id": 1486,
            "name": "group"
        }
        ...
    ]
}
```

**Errors**

* 403 Permission error, only administrator can perform this action

### <a id="admin-only-delete-a-group"></a>Delete a Group

Available for Seafile v6.0.0+

**DELETE** https://cloud.seafile.com/api/v2.1/admin/groups/{group_id}/

**Sample request**

    curl -X DELETE -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/admin/groups/1486/

**Sample response**

```
{"success":true}
```

**Errors**

* 403 Permission error, only administrator can perform this action

### <a id="admin-only-transfer-a-group"></a>Transfer a Group

Available for Seafile v6.0.0+

**PUT** https://cloud.seafile.com/api/v2.1/admin/groups/{group_id}/

**Sample request**

    curl -X PUT -d "new_owner=1@1.com" -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/admin/groups/1528/

**Sample response**

```
{
    "owner": "1@1.com",
    "created_at": "2016-08-04T17:34:05+08:00",
    "id": 1528,
    "name": "test_group"
}
```

**Errors**

* 403 Permission error, only administrator can perform this action
* 404 User not found.
* 500 Internal Server Error

### <a id="admin-only-get-group-libraries"></a>Get Group Libraries

Available for Seafile v6.0.0+

**GET** https://cloud.seafile.com/api/v2.1/admin/groups/{group_id}/libraries/

Get all libraries of a group.

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/groups/64/libraries/

**Sample response**

```
[
    {
        "repo_id":"7460f7ac-a0ff-4585-8906-bb5a57d2e118",
        "name":"My Library",
        "permission":"rw",
        "group_id":65,
        "shared_by":"lian@lian.com",
        "size":97662
    }
]
```

**Errors**

* 403 Permission error, only administrator can perform this action
* 404 Group not found.

### <a id="admin-only-delete-group-library"></a>Delete Group Library

Available for Seafile v6.0.0+

**DELETE** https://cloud.seafile.com/api/v2.1/admin/groups/{group_id}/libraries/{repo_id}/

**Sample request**

    curl -X DELETE -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/admin/groups/64/libraries/7460f7ac-a0ff-4585-8906-bb5a57d2e118/

**Sample response**

```
{"success":true}
```

**Errors**

* 403 Permission error, only administrator can perform this action
* 404 Library/Group not found.
* 500 Internal Server Error

### <a id="admin-only-get-group-members"></a>Get Group Members

Available for Seafile v6.0.0+

**GET** https://cloud.seafile.com/api/v2.1/admin/groups/{group_id}/members/

Get all members of a group.

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/groups/64/members/

**Sample response**

```
[
    {
        "login_id":"",
        "avatar_url":"https://cloud.seafile.com/media/avatars/0/1/a72299021077701e7c522c46fdaa87/resized/80/6ad30837f69ea7ef234dc272fb15e9e9.png",
        "contact_email":"lian@lian.com",
        "name":"name of lian",
        "is_admin":true,
        "role":"Owner",
        "group_id":65,
        "email":"lian@lian.com"
    },
    {
        "login_id":"",
        "avatar_url":"https://cloud.seafile.com/media/avatars/default.png",
        "contact_email":"1@1.com",
        "name":"123",
        "is_admin":false,
        "role":"Member",
        "group_id":65,
        "email":"1@1.com"
    }
]
```

**Errors**

* 403 Permission error, only administrator can perform this action
* 404 Group not found.

### <a id="admin-only-delete-group-member"></a>Delete Group Member

Available for Seafile v6.0.0+

**DELETE** https://cloud.seafile.com/api/v2.1/admin/groups/{group_id}/members/{email}/

**Sample request**

    curl -X DELETE -H 'Authorization: Token 444d2bbf1fc78ffbeedc4704c9f41e32d926ac94' https://cloud.seafile.com/api/v2.1/admin/groups/64/members/foo@foo.com/

**Sample response**

```
{"success":true}
```

**Errors**

* 403 Permission error, only administrator can perform this action
* 403 foo@foo.com is group owner, can not be removed.
* 404 Group not found.
* 500 Internal Server Error

### <a id="admin-only-add-group-member"></a>Add Group Member

Available for Seafile v6.0.8+

**POST** https://cloud.seafile.com/api/v2.1/admin/groups/{group_id}/members/

**Sample request**

    curl -d "email=1@1.com&email=2@1.com" -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' https://cloud.seafile.com/api/v2.1/admin/groups/65/members/

**Sample response**

```
{
    "failed":[
        {
            "email":"2@1.com","error_msg":"User 2@1.com is already a group member."
        }
    ],
    "success":[
        {
            "login_id":"",
            "avatar_url":"https://cloud.seafile.com/media/avatars/default.png",
            "contact_email":"8@1.com",
            "name":"name of 8",
            "is_admin":0,
            "role":"Member",
            "group_id":65,
            "email":"8@1.com"
        }
    ]
}
```

**Errors**

* 400 email invalid.
* 404 Group not found.

### <a id="admin-only-update-group-member-role"></a>Update Group Member Role

Available for Seafile v6.0.8+

##### Set a group member as admin

**PUT** https://cloud.seafile.com/api/v2.1/admin/groups/{group_id}/members/{email}

**Sample request**

    curl -X PUT -d "is_admin=true" -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' https://cloud.seafile.com/api/v2.1/admin/groups/65/members/3@1.com/

**Sample response**

```
{
    "login_id":"",
    "avatar_url":"https://cloud.seafile.com/media/avatars/default.png",
    "contact_email":"3@1.com",
    "name":"update name of 3",
    "is_admin":1,
    "role":"Admin",
    "group_id":65,
    "email":"3@1.com"
}
```

**Errors**

* 400 email invalid.
* 400 is_admin invalid.
* 404 Group/User not found.
* 500 Internal Server Error

##### Unset a group member as admin

**PUT** https://cloud.seafile.com/api/v2.1/admin/groups/{group_id}/members/{email}

**Sample request**

    curl -X PUT -d "is_admin=false" -H 'Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a' https://cloud.seafile.com/api/v2.1/admin/groups/65/members/3@1.com/

**Sample response**

```
{
    "login_id":"",
    "avatar_url":"https://cloud.seafile.com/media/avatars/default.png",
    "contact_email":"3@1.com",
    "name":"update name of 3",
    "is_admin":0,
    "role":"Member",
    "group_id":65,
    "email":"3@1.com"
}
```

**Errors**

* 400 email invalid.
* 400 is_admin invalid.
* 404 Group/User not found.
* 500 Internal Server Error

## <a id="admin-only-log"></a>Admin Log

### <a id="admin-only-get-login-log"></a>Get Login Log

This api is only supported in pro edition.

**GET** https://cloud.seafile.com/api/v2.1/admin/logs/login/?start=2016-03-20&end=2016-03-31

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/logs/login/?start=2016-03-20&end=2016-03-31

**Sample response**

```
[
    {
        'email': u'lian@lian.com',
        'login_ip': u'192.168.1.124',
        'name': u'lian',
        'login_time': '2016-03-31T14:42:23+08:00'
    },
    {
        'email': u'org@org.com',
        'login_ip': u'192.168.1.124',
        'name': u'org',
        'login_time': '2016-03-31T14:39:08+08:00'
    }
]
```

**Errors**

* 400 start or end date invalid.
* 403 Feature disabled.

### <a id="admin-only-get-file-audit-log"></a>Get File Audit Log

This api is only supported in pro edition.

**GET** https://cloud.seafile.com/api/v2.1/admin/logs/file-audit/?start=2016-03-20&end=2016-03-31

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/logs/file-audit/?start=2016-03-20&end=2016-03-31

**Sample response**

```
[
    {
        'repo_id': u'4929d0df-8c6c-43cb-8edf-40a8489689fb',
        'time': '2016-03-31T05:46:03+08:00',
        'etype': u'file-download-web',
        'ip': u'192.168.1.124',
        'user_name': u'org',
        'file_path': u'/earth.jpg',
        'user_email': u'org@org.com',
        'repo_name': ''
    },
    {
        'repo_id': u'513cd72c-c54a-463e-a18f-841efe91bd61',
        'time': '2016-03-31T06:25:22+08:00',
        'etype': u'file-download-web',
        'ip': u'192.168.1.124',
        'user_name': u'org',
        'file_path': u'/kj.md',
        'user_email': u'org@org.com',
        'repo_name': u'new-lib-of-org-1'
    }
]
```

**Errors**

* 400 start or end date invalid.
* 403 Feature disabled.

### <a id="admin-only-get-file-update-log"></a>Get File Update Log

This api is only supported in pro edition.

**GET** https://cloud.seafile.com/api/v2.1/admin/logs/file-update/?start=2016-03-20&end=2016-03-31

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/logs/file-update/?start=2016-03-20&end=2016-03-31

**Sample response**

```
[
    {
        'commit_id': u'55ec5350b16d6c72a044b5a9cd9b2d62ad439364',
        'file_operation': u'Added "user.csv".',
        'repo_id': u'513cd72c-c54a-463e-a18f-841efe91bd61',
        'repo_name': u'new-lib-of-org-1',
        'time': '2016-03-31T06:25:15+08:00',
        'user_email': u'org@org.com',
        'user_name': u'org'
    },
    {
        'commit_id': u'6820d809481e3c9fb856d0650ac73a09b570a301',
        'file_operation': u'Added "kj.md"',
        'repo_id': u'513cd72c-c54a-463e-a18f-841efe91bd61',
        'repo_name': u'new-lib-of-org-1',
        'time': '2016-03-31T06:25:21+08:00',
        'user_email': u'org@org.com',
        'user_name': u'org'
    }
]
```

**Errors**

* 400 start or end date invalid.
* 403 Feature disabled.

### <a id="admin-only-get-perm-audit-log"></a>Get Permission Audit Log

This api is only supported in pro edition.

**GET** https://cloud.seafile.com/api/v2.1/admin/logs/perm-audit/?start=2016-03-20&end=2016-03-31

**Sample request**

    curl -H "Authorization: Token f2210dacd9c6ccb8133606d94ff8e61d99b477fd" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/logs/perm-audit/?start=2016-03-20&end=2016-03-31

**Sample response**

```
[
    {
        'etype': u'add-repo-perm',
        'file_path': u'/folder',
        'from_email': u'org3@org3.com',
        'from_name': u'org3',
        'permission': u'rw',
        'repo_id': u'a84544e5-0b84-459d-b1e6-0399dabc76a0',
        'repo_name': '',
        'time': '2016-03-31T06:21:50+08:00',
        'to': u'org@org.com'
    },
    {
        'etype': u'add-repo-perm',
        'file_path': u'/folder',
        'from_email': u'org3@org3.com',
        'from_name': u'org3',
        'permission': u'rw',
        'repo_id': u'a84544e5-0b84-459d-b1e6-0399dabc76a0',
        'repo_name': '',
        'time': '2016-03-31T06:21:53+08:00',
        'to': u'777'
    }
]
```

**Errors**

* 400 start or end date invalid.
* 403 Feature disabled.

## <a id="admin-only-organization"></a>Organization

### <a id="admin-only-add-organization"></a>Add Organization

This api is only supported in pro edition.

**POST** https://cloud.seafile.com/api2/organization/

**Request parameters**

* username
* password
* org_name
* prefix
* quota
* member_limit

**Sample request**

    curl -v -X POST -d "username=example@example.com&password=example&org_name=example&prefix=example&quota=100&member_limit=10" -H "Authorization: Token ccdff90e4d1efe76b2b3d91c06b027a5cff189d4" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api2/organization/

**Sample response**

    "success"

### <a id="admin-only-add-organization-user"></a>Add Organization User

This api is only supported in pro edition (since 6.0.9).

**POST** https://cloud.seafile.com/api/v2.1/admin/organizations/{org_id}/users/

**Request parameters**

* org_id
* email
* password

**Sample request**

    curl -X POST -d "email=6@org.com&password=6" -H "Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/organizations/160/users/

**Sample response**

```
{
    "active": true,
    "contact_email": "6@org.com",
    "org_id": 160,
    "email": "6@org.com",
    "name": "6"
}
```

**Errors**

* 400 org_id invalid.
* 400 email invalid.
* 400 password invalid.
* 400 User already exists.
* 403 The number of users exceeds the limit.
* 403 Failed. You can only invite %d members.
* 404 Organization not found.
* 500 Fail to add user.
* 500 Internal Server Error

### <a id="admin-only-delete-organization-user"></a>Delete Organization User

This api is only supported in pro edition (since 6.0.9).

**DELETE** https://cloud.seafile.com/api/v2.1/admin/organizations/{org_id}/users/{email}/

**Request parameters**

* org_id
* email

**Sample request**

    curl -X DELETE -H "Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/organizations/160/users/6@org.com/

**Sample response**

```
{
    "success": true
}
```

**Errors**

* 400 org_id invalid.
* 403 Failed to delete: is an organization creator.
* 404 Organization not found.
* 404 User not found.
* 500 Internal Server Error

### <a id="admin-only-modify-organization-user"></a>Modify Organization User

This api is only supported in pro edition (since 6.0.9).

**PUT** https://cloud.seafile.com/api/v2.1/admin/organizations/{org_id}/users/{email}/

**Request parameters**

* org_id
* email
* active, `true` or `false`

**Sample request**

    curl -X PUT -d "active=false" -H "Authorization: Token 0eb24ce5db35a31f70171eca2f760f03f59fa09a" -H 'Accept: application/json; indent=4' https://cloud.seafile.com/api/v2.1/admin/organizations/160/users/4@org.com/

**Sample response**

```
{
    "active": false,
    "contact_email": "4@org.com",
    "org_id": 160,
    "email": "4@org.com",
    "name": "4"
}
```

**Errors**

* 400 org_id invalid.
* 400 active invalid.
* 400 active invalid, should be 'true' or 'false'.
* 404 Organization not found.
* 404 User not found.
* 500 Internal Server Error
