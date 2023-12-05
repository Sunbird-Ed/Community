# Onboarding of Users

1. _**Guest user onboarding**_

![Onboarding steps for a guest user:: Language, user roles, board/medium/class and location](<../../../../../.gitbook/assets/Screen Shot 2022-02-23 at 8.04.47 AM.png>)

Allowing users to access content w/o forcing them to log in lowers friction for users. Sunbird ED has a set of guest onboarding steps that can be configured. For example, for a schooling use case, you may need to capture board, medium, and grade in order to provide relevant content suggestions. But for a university use case, you may need to capture the degree, medium, and semester. The configuration can also be by the persona. For eg, a teacher may declare their board, medium, class, and subject, whereas a student may have to only declare their board, medium, and class only as they study all subjects. It can also be configured based on the combination of persona + location. The Learning app has these 4 onboarding steps, but they can be changed, and reordered as well via configurations.

_**2. Logged in user onboarding**_

![Onboarding steps for a logged-in user: Registration. Social login. Third party system login.](<../../../../../.gitbook/assets/Screen Shot 2022-02-23 at 8.10.16 AM.png>)

You can allow users to log in. It can be set up as an optional or mandatory step - via a Sunbird login (through a registered mobile number or email ID), social login (while Gmail integration comes out of the box, it can be easily extended to other types of social logins) or any 3rd party authentication mechanisms (let's say you have your own user auth tool, Sunbird exposes SSO APIs so that users can be verified via this tool and use the same credentials). Further, content preferences, location, or anything more can be captured as part of the login process.

_**3. Multiple users on the same device**_

![](<../../../../../.gitbook/assets/Profile page.PNG>)

In a country like India, devices are often shared. For example, there may be one phone in a household which needs to be shared between two children at home. Or there may be an NGO that is going out to the field to work with some teachers, but they only have one or two tablets with them\_**.**\_ Hence, this capability allows multiple users to create “managed users or profiles” on the same device, so that they can switch between profiles. Each profile contains the learning history & preferences of the user so they can pick up from where they last left off.
