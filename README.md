# Assistent

- [[#Goal|Goal]]
- [[#Risks|Risks]]
- [[#User Journey|User Journey]]
	- [[#User Journey#Onboard|Onboard]]
	- [[#User Journey#confirm reminder times|confirm reminder times]]
	- [[#User Journey#User confirm|User confirm]]
	- [[#User Journey#Receive helpful meeting preparation|Receive helpful meeting preparation]]
	- [[#User Journey#Confirm update|Confirm update]]


## Goal
make it easier to prepare, conduct and follow-up in regular meetings

## Risks

TODO: Risk matrix
- Usability
	- muss owner und participants so gut gefallen das sie es auch nutzen wollen
	- Async: Email integration needs to be first
	- Sync: right moment and user experience for synchronous interaction
- Integration
	- Email tool must be just right
		- able to setup mailboxes and receive emails
		- professional in sending mails because of spam folders
		- affordable
		- not so extendible for the prototype and possibly mvp
		- integrate well with MS Office
	- MVP: support custom domain agendaflex recur 
- Architecture
	- Mandantentrennung später Cloud Service
	- one mailbox per meeting series

## User Journey

### Onboard

Ich schicke meine Einladung an emailadresse@agendaflex.com

#mvp 
### confirm reminder times

bekomme Email zurück mit Terminvorschlag um das Meeting vorzubereiten

TODO
- [ ] setup mailserver (mailchimp?)
	- [ ] has API?
	- [ ] check if it can receive emails

Azure Function App to trigger MS communication services (alt. sendgrid or mailgun)

- [ ] read calendar invite
- [ ] setup Azure function or otherwise cron job
- [ ] all emails get commited to a git repo
	- [ ] merge request to confirm email sending
- [ ] send email to confirm regular email

MVP
- invite other participants to sign up for the service for free
- offer 1 free series of their own

### User confirm

Ich bestätige die Uhrzeit

MVP
- parse ok from response
- Interactive Button in Email leads to further options
	- checklists
	- metrics

### Receive helpful meeting preparation

Zur ausgemachten Uhrzeit bekomme ich eine Email mit Link

- [ ] template as mailto Link to
      Klick auf Link öffnet Entwurf mit Agenda für nächstes Meeting

### Confirm update

listen owner: ich erhalte eine Email dass die Updates empfangen wurden
	- MVP
		- Checklisten
		- Metriken

- [ ] receive email with participants
- [ ] implement onboarding



### Initial Repository Structure

- ~~**`/ADRs`**: Directory for Architectural Decision Records. Each ADR will be a markdown file (.md) describing decisions like technology choices, architectural patterns, and significant methodologies with justifications.
- **`/src`**: Source code directory.
    - **`/email_integration`**: Contains all source code related to email integration for asynchronous communication. Given the emphasis on email integration as a first step, dedicate a space for its development.
    - **`/sync_interaction`**: For synchronous interaction code, addressing the right moment and user experience.
    - **`/mvp_features`**: MVP-specific features like sign-up services, free series offerings, etc.
- **`/tests`**: For all test scripts and automation related to continuous integration and testing strategies, adhering to ISO 26262-6:2018 recommendations for software testing and verification in automotive systems​​.
- **`/docs`**: Project documentation, including setup guides, feature documentation, and user manuals.
    - **`/meeting_templates`**: Meeting preparation templates and checklists.
- ~~**`/requirements`**: Captures and documents all project requirements, structured around the ASIL levels mentioned. This folder will contain a detailed breakdown of system and software requirements, including usability and integration concerns​​​​.
- **`/tools`**: Custom tools developed or used for the project, including any scripts for automation and CI/CD pipeline setups.
- ~~**`/CI_CD`**: Configuration files and scripts for Continuous Integration and Continuous Deployment, considering the emphasis on automating build systems and regression tests as suggested by ISO 26262-6:2018​​.