## Repository Types

1- Proxy Respository:

This is a repository that is linked to a remote respository. For example, Maven central respositoy is a remote public repository for Maven artifacts. If you are a developer, can download jar file, dependencies and other artifacts.

2- Hosted Repository:

This is a repository that is the primary storage for artifacts and components, for example for company own components.

maven-snapshots => only used for development artifacts
maven-releases => used for production releases. it can also be used to store commercial libraries which are not publicly available via maven central repository.

3- Group Repository:

This repository allows you to combine multiple repositories or even other repository groups in a single repository. Developers can use sinlge url for thier applications which will give them access to multiple repositories.