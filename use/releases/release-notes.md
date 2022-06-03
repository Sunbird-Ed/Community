# Release notes

{% file src="../../.gitbook/assets/Sunbird ED 4.7.0.pdf" %}

{% file src="../../.gitbook/assets/Sunbird ED 4.9.1.pdf" %}

Release Notes

June 1, 2022

SunbirdED Release Notes

Document Version History

| Version Number | Original / Modified | Authored / Modified By | Date         |
| -------------- | ------------------- | ---------------------- | ------------ |
| 1              | Original            | Documentation Team     | June 1, 2022 |

About this Document

This document provides details of features and enhancements made to the Sunbird platform for the release version 4.9.1

Release Version

| Project | Release Date | Release version    |
| ------- | ------------ | ------------------ |
| 1       | June 1, 2022 | Documentation Team |

1

SunbirdED Release Notes

New Features

| No. | Feature                                 | Description                                                                                                                                                                                                                               | Ticket No.         |
| --- | --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------ |
| 1   | Caption and transcript for video player | Users will be able to access and download the transcripts and read along with the captions                                                                                                                                                | SB-29992, SB-26455 |
| 2   | Enhanced UI                             | Enhanced UI of the profile page                                                                                                                                                                                                           | SB-29714           |
| 3   | Implement collection APIs               | Implement clients to call new collection APIs instead of content APIs                                                                                                                                                                     | SB-25929           |
| 4   | Optimize bundle size of portal          | <p>Currently the bundle size of portal is in MB. Enabled the bundle size optimization by the following three steps:</p><ol><li>Removing redundant libraries</li><li>Removing Unused Code</li><li>Removing Unused CSS libraries.</li></ol> | SB-28070           |

Enhancements / Technical tasks

| No. | Description                                                                                                                                                 | Project          | Issue No.          |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- | ------------------ |
| 1   | The accessibility features are enhanced to make the application more accessible to the users                                                                | Sunbird Platform | SB-29919, SB-29903 |
| 2   | Desktop app invokes Refresh token APIs when a user logs in to get a new access token to access APIs. The new access token will have the roles of the users. | Sunbird Platform | SB-27999           |
| 3   | Desktop app enhanced to invoke /api route instead of /learner route for managed user API                                                                    | Sunbird Platform | SB-27037           |

Known Issues and Suggested Solution

Note: This release does not have any known issues with suggested workaround solutions Issue Tracker

| No. | Issue No. | Description                                                                   | Status   | Project                 |
| --- | --------- | ----------------------------------------------------------------------------- | -------- | ----------------------- |
| 1   | SB-27104  | Offline Desktop: Learner passbook section is not available in profile section | Released | Sunbird Portal Platform |

2

SunbirdED Release Notes

| 2 | SB-29991 | Offline Desktop: Role selection popup is appearing twice while onboarding                                        | Released | Sunbird Portal Platform |
| - | -------- | ---------------------------------------------------------------------------------------------------------------- | -------- | ----------------------- |
| 3 | SB-29690 | User is unable to consume the question set inside the content playlist and digital textbook in the desktop app   | Released | Sunbird Portal Platform |
| 4 | SB-27577 | Offline Desktop: Banners are not configured                                                                      | Released | Sunbird Portal Platform |
| 5 | SB-29162 | Accessibility UI issue in portal. The tooltip disappears on hovering over the India map                          | Released | Sunbird Portal Platform |
| 6 | SB-29593 | For anonymous user , the total count in the explore page of the contributing partner shows incorrect count value | Released | Sunbird Portal Platform |
| 7 | SB-22682 | Course certificate messages are not highlighted in the expected colors                                           | Released | Sunbird Portal Platform |

3
