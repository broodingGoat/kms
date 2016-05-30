Who are the users?
* Developers who want to store credentials for their applications or use
* System Admins who want to store system credentials, ssh keys
* Regular users who might have credentials
* Vendors or solution providers who would want to share credentials
* University professors who would want to share credentials with users
* Systems that need to communicate with each other
* Groups of above users who want to share credentials amongst themselves

What is the special need of our users?
* Secure system
* Ease of use. Be able to use it from variety of systems in various scenarios
* Contextual metadata with what is being stored
* Easy ability to share credentials

Use Cases
* Store application credentials




Basic capabilities
* Store existing username & password with a "for-tag" for a team
* Store existing ssh-key with a "for-label" & "server-tag" (optional) for team
* Get username & password for a team, with a "for-tag"
* Get ssh-key for a team, with a "for-label"
* Get ssh-key for a team, with a "for-label"

Future capabilities
* Authenticate for a team

What to build
* API
* CLI invoking of API

Details
* API
GET /kms/team/$team-name/?tag=$tag-pair,$tag-pair

e.g. of tag-pair -

for:development
for:godaady.com
for:wordpress
server:abc.example.com



