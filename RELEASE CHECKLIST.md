# Release checklist

A Bike Sync update is not complete until:

1. The release notes and cumulative update log contain the new version.
2. Both Intel and Apple-silicon builds and compatibility tests pass.
   Run source and test validation before the release build. Do not rebuild and
   re-sign intermediate UI revisions. The app's build signs the nested updater
   ad hoc and accesses the stable developer identity only once for the enclosing
   application.
3. The update package is signed with the Keychain-protected publisher key.
   Reuse the stable `Build-2.4.13/UpdatePublisher` executable; recompiling the
   helper changes its Keychain identity and can cause an avoidable password prompt.
4. The GitHub release asset and `latest.json` are published and independently verified.
5. Update discovery and package preparation succeed when tested as an older app version.
6. The running Bradley app, Baby Bison installer folder, and Paul's Evolution installer subfolder all contain the matching verified release. Each shared installer folder must contain exactly one installer ZIP, `READ ME.html`, and `VERSION LOG.txt`—never a source archive.

No athlete data, credentials, routes, health information, or private coaching data belong in this repository.
