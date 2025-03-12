# Rocky8Stig
Files that help stig audits produce accurate information regarding Rocky 8 False Negatives

Rocky 8 stig auditing files do not correctly check for rocky linux. This causes some of the checks to fail. The 4 files provided have been updated to replace rhel-release, Redhat Enterprise release and and other rhel sections with rocky-release, Rocky Linux release and rocky. This allows for accurate auditing to be run. 

Instructions:
Download the 4 files and upload to a Rocky 8 stig hardened server. Place in the /usr/share/xml/scap/ssg/content folder. Backup the original files in the folder. Run the command again, for example, "oscap xccdf eval --report <reportname>.html --profile stig /usr/share/xml/scap/ssg/content/ssg-rl8-ds.xml"
NOTE: Make sure the files are owned by root:root

Checks:
Compare a report run prior to the file changes and notice results that failed that show passed. Supported vendor is one such check. Some crypto checks also revolve around the correctly reported OS as many do rpm checks against the rocky-release rpm.
