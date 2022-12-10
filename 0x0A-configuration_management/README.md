# Configuration managemets                                                                

# Background Context                                                                                                                    
When I was working for SlideShare, I worked on an auto-remediation tool called <a href = "https://engineering.linkedin.com/slideshare/sk
ynet-project-_-monitor-scale-and-auto-heal-system-cloud">Skynet</a> that monitored, scaled and fixed Cloud infrastructure. I was using a
parallel job-execution system called MCollective that allowed me to execute commands to one or multiple servers at the same time. I cou
ld apply an action to a selected set of servers by applying a filter such as the server’s hostname or any other metadata we had (server 
type, server environment…). At some point, a bug was present in my code that sent nil to the filter method.                             

There were two pieces of bad news;                                                                                                      
* When MCollective receives nil as an argument for its filter method, it takes this to mean "all servers"                               
* The action I sent was to terminate the selected servers                                                                               

I started the parallel job-execution and after some time, I realized that it was taking longer than expected. Looking at logs I realized
that I was shutting down SlideShare’s entire document conversion environment. Actually, 75% of all our conversion infrastructure server
s had been shut down, resulting in users not able to convert their PDFs, powerpoints, and videos… Pretty bad!                           

Thanks to Puppet, we were able to restore our infrastructure to normal operation in under 1H, pretty impressive. Imagine if we had to do
everything manually: launching the servers, configuring and linking them, importing application code, starting every process, and obvio
usly, fixing all the bugs (you should know by now that complicated infrastructure always goes sideways)…                                

Obviously writing Puppet code for your infrastructure requires an investment of time and energy, but in the long term, it is for sure a 
must-have.                                                                                                                              

# Resources                                                                                                                             
* <a href = "https://www.digitalocean.com/community/tutorials/an-introduction-to-configuration-management">Intro to Configuration Manage
ment</a>                                                                                                                                
* <a href = "https://puppet.com/docs/puppet/5.5/types/file.html">Puppet resource type: file</a>                                         
* <a href = "https://puppet.com/blog/puppets-declarative-language-modeling-instead-of-scripting/">Puppet’s Declarative Language: Modelin
g Instead of Scripting</a>                                                                                                              
* <a href = "http://puppet-lint.com/">Puppet lint</a>                                                                                   
* <a href = "https://github.com/voxpupuli/puppet-mode">Puppet emacs mode</a>                                                            

# Requirements                                                                                                                          

# General                                                                                                                               
* All your files will be interpreted on Ubuntu 20.04 LTS                                                                                
* All your files should end with a new line                                                                                             
* A README.md file at the root of the folder of the project is mandatory
* Your Puppet manifests must pass puppet-lint version 2.1.1 without any errors
* Your Puppet manifests must run without error
* Your Puppet manifests first line must be a comment explaining what the Puppet manifest is about
* Your Puppet manifests files must end with the extension .pp
