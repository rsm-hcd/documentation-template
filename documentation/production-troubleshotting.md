# Production Troubleshooting
> Any issues that have been encountered and resolved can be defined here. This will be a starting point for a developer jumping into a project trying to troubleshoot the production environment.

**Issue**: _Unable to `git pull` on production environment. Getting a 'File cannot be overwritten error.'_

**Solution**: Shutdown the IIS worker process, and then `git pull`. Then start the worker process again once the pull is completed.