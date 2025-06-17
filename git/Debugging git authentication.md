# General notes
## Using SSH  
GIT communicates using the first SSH key that is valid for general communication to the remote.
This behavior causes authorisation issues if there are multiple keys that are authorized for use with the remote, but only some of those keys are authorized for the specific repository.
Check order of keys in the SSH config in such a case.
### Enable SSH debugging in GIT
`GIT_SSH_COMMAND="ssh -v" git push`
