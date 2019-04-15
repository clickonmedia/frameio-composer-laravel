# Frame.io PHP Client

```
run the following command to install the package
composer require clickonmedia/frameio-php-client
```


## Basic Usage

```
use Frameio\FrameIOClient;
$frameIO =  new FrameIOClient("TOKEN");
```


## All available functions

**Get user profile**

```
$frameIO->getProfile()
```


**Gets teams for a user**

*NOTE: This currently returns an error because of a bug in Frame.io API*
```
$frameIO->getTeams()
```


**Get user membership for a team**

*NOTE: This currently returns an error because of a bug in Frame.io API*

> @param string $teamId Member Role (required)

```
$frameIO->getTeamMembership( $teamId )
```


**Add user membership to a team**

> @param string $teamId Member Role (required)<br />
> @param string $userId Member Role (required)<br />
> @param string $role Member Role (required)

```
$frameIO->addTeamMembership( $teamId, $userId, $role )
```


**Create project**

> @param string $name Project name (default value: Current Time)<br />
> @param boolean $private Set project as private (required)

```
$frameIO->createProject( $name , $private )
```


**Get project by id**

> @param string $projectId Project ID (required)

```
$frameIO->getProjectById( $projectId )
```


**Delete project by id**

> @param string $projectId Project ID (required)

```
$frameIO->deleteProjectById( $projectId )
```


**Get user membership for project**

> @param string $projectId Project ID (required)

```
$frameIO->getUserMembershipForProject( $projectId )
```


**Add a collaborator to a team**

> @param string $projectId Project ID (required)<br />
> @param string $email User email address (required)

```
$frameIO->addCollaboratorToTeam( $projectId, $email )
```


**Create an asset**

> @param string $rootAssetId Parent asset ID (required)<br />
> @param string $name name (required)<br />
> @param int $filesize filesize (required)<br />
> @param string $description description (default Value: "")<br />
> @param string $type type  (default value: "file")<br />
> @param string $filetype filetype  (default value: "mp4")<br />
> @param string $fileUrl fileUrl  (default value: "")<br />
> @param array $properties properties  (default value: []/key value pair array)

```
$frameIO->createAsset( $rootAssetId, $name, $filesize, $description, $type, $filetype, $fileUrl, $properties)
```


**Get assets**

> @param string $rootAssetId Parent asset ID (required)<br />
> @param string $name Type (default value: "file")

```
$frameIO->getAssets( $rootAssetId, $type )
```


**Get an Asset by ID**

> @param string $assetId Asset ID (required)

```
$frameIO->getAssetById( $assetId )
```


**Update an Asset**

> @param string $assetId Asset ID (required)<br />
> @param string $name Name (default value: "")<br />
> @param string $description Description (default value: "")<br />
> @param string $properties Properties (default value: []/key value pair array)

```
$frameIO->updateAssetById( $assetId, $name, $description, $properties )
```


**Delete an Asset By ID**

> @param string $assetId Asset ID (required)

```
$frameIO->deleteAssetById( $assetId )
```


**Add a version to an Asset**

> @param string $assetId Asset ID (required)<br />
> @param string $nextAssetId Next Asset ID (required)

```
$frameIO->addVersionToAsset( $assetId, $nextAssetId )
```


**Create a Comment**

> @param string $assetId Asset ID (required)<br />
> @param string $text text (default value : "")<br />
> @param string $annotation annotation (default value : "")<br />
> @param string $timestamp timestamp (default value : "")<br />
> @param string $napageme napageme (default value : "")<br />
> @param string $pitch pitch (default value : "")<br />
> @param string $yaw yaw (default value : "")

```
$frameIO->createComment( $assetId, $text, $annotation, $timestamp, $page, $pitch, $yaw)
```


**Get Comments By Asset Id**

> @param string $assetId Asset ID (required)

```
$frameIO->getComments( $assetId )
```


**Get Comment By Comment Id**

> @param string $commentId Comment ID (required)

```
$frameIO->getCommentById( $commentId )
```


**Update a Comment**

> @param string $commentId Comment ID (required)<br />
> @param string $text text (default value : "")

```
$frameIO->updateComment( $commentId, $text )
```


**Delete a Comment**

> @param string $commentId Comment ID (required)

```
$frameIO->deleteCommentById ( $commentId )
```


**Get Review Links for Project**

> @param string $projectId Project ID (required)

```
$frameIO->getReviewLinks( $projectId )
```


**Create a Review Link**

> @param string $projectId Project ID (required)<br />
> @param string $name Review link name (required)<br />
> @param boolean $allowApprovals Allow Approvals (default value : false)<br />
> @param boolean $currentVersionOnly Project ID (default value : false)<br />
> @param boolean $enableDownloading Project ID (default value : false)<br />
> @param boolean $requiresPassphrase Project ID (default value : false)<br />
> @param string $password Project ID (default value : "")<br />
> @param string $expiresAt Project ID (default value : "")


```
$frameIO->createReviewLink( $projectId, $name, $allowApprovals, $currentVersionOnly, $enableDownloading, $requiresPassphrase, $password, $expiresAt )
```


**Update a Review Link**

> @param string $reviewLinkId Review link ID (required)<br />
> @param string $name Review name (required)<br />
> @param boolean $allowApprovals Allow Approvals (default value : false)<br />
> @param boolean $currentVersionOnly Current Version Only (default value : false)<br />
> @param boolean $enableDownloading Enable Downloading (default value : false)<br />
> @param boolean $requiresPassphrase Requires Passphrase (default value : false)<br />
> @param string $password password (default value : "")<br />
> @param string $expiresAt Allow Approvals (default value : "")

```
$frameIO->UpdateReviewLink( $reviewLinkId, $name, $allowApprovals, $currentVersionOnly, $enableDownloading, $requiresPassphrase, $password, $expiresAt )
```


**Get a Review Link**

> @param string $link_id Review link ID (required)

```
$frameIO->getReviewLink( $link_id )
```


**Get Review Link Items**

> @param string $link_id Review link ID (required)

```
$frameIO->getReviewLinkItems( $link_id )
```


**Add Assets to a Review Link**

> @param string $reviewLinkId Review link ID (required)<br />
> @param array $assetIds Asset IDs (required, Array of ids)

```
$frameIO->addAssetsToReviewLink( $reviewLinkId, $assetIds )
```


**Search for Assets**

> @param string $query Search query (default value : "")<br />
> @param string $teamId Team ID (default value : "")<br />
> @param string $accountId Account ID (default value : "")

```
$frameIO->getSearchAssets ( $query, $teamId, $accountId )
```


**Search for Assets (Complex)**

> @param string $query Search query (default value : "")<br />
> @param string $teamId Team ID (default value : "")<br />
> @param string $accountId Account ID (default value : "")<br />
> @param string $filter Filter for the query (default value : [], key value pair Array)

```
$frameIO->searchAssets ( $query , $teamId , $accountId, $filter )
```

## Frame.io API Documentation

https://docs.frame.io/reference

## Run tests

```
composer run-script test
