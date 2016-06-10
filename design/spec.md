What is our goal?
* Design a modern key management system
* Design it for user adoption

Who are the users?
* Developers who want to store credentials for their applications or other tools they use
* System Admins who want to store system credentials, ssh keys
* Regular users who might have personal credentials
* Vendors or solution providers who would want to share credentials for their products & services
* University professors who would want to share credentials among students
* Systems that need to communicate with each other
* Groups of above users who want to share credentials amongst themselves

What is the special need of our users?
* Secure system
* Ease of use. Be able to use it from variety of systems & in various scenarios
* Contextual metadata with what is being stored
* Easy ability to share credentials

Possible Use Cases: A user would want to
1. Store application & system credentials
2. Store keys, long living tokens
3. Associcate credentials with some meta data & have ability to update it
4. Fetch & use the credentials with least friction
5, Manage access to the credentials & define who all have access to it
6. Have periodic reporting or notification of who all have access, when the credentials were requested 
7. Define differnt roles in terms of who can add, modify or remove credentials, as well as acess to it


Basic capabilities
* Define construct of team & roles.
* Store existing username & password with a "for-tag" for a team
* Store existing ssh-key with a "for-label" & "server-tag" (optional) for team
* Get username & password for a team, with a "for-tag"
* Get ssh-key for a team, with a "for-label"
* Push & Get ssh-key for a team, with a "for-label"
* Define simple CLI utilities (KMS CLI) to interact with the service
* Define a simple Web UI to interact with the service

Future capabilities
* Enable service for different identity providers
* Build reporting & monitoring capability to audit usage
* Define interafaces for the service to be used by other "services" (e.g. SaaS providers)
* Define concept of short life teams, for sharing credentials between 2 different entities
* SSH CLI which natively integrates with the KMS CLI

What to build
* API
* CLI invoking & encapsulating API

Details
* API example
```
# credential management
GET /kms/team/$team-name/?tag=$tag-pair,$tag-pair # get credential
POST /kms/team/$team-name/ # create or modify credentials
JSON Body 
{
    "item":[
            {
                "name": "some-credential",
                "type": "credential",
                "credential": {
                    "username": "some username",
                    "password": "some password"
                }
            },
            {}
    ]
}
DELETE /kms/team/$team-name/$id # delete credentials

# team management
POST /kms/manage-team/$team-name # create team
GET /kms/manage-team # get list of teams

```
e.g. of tag-pair -
```
for:development
for:godaady.com
for:wordpress
server:abc.example.com
```


