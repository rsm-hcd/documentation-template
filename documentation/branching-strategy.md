# Branching Strategy
> Lists the different branches and what their roles are. Also indicates what merging process is to go from feature development all the way through to production.

Table of Contents
=================
* [Branches](#branches)
    * [development](#development)
    * [working](#working)
    * [staging](#staging)
    * [master](#master)
* [Workflow](#workflow)

## Branches

### development
> This represents development features for the current sprint.

### working
> This represents features for the current sprint to be tested by QA.

### staging
> This represents features that are ready for the client's review.

### master
> This represents the current production code base.

## Workflow
1. When a new feature is being developed a new feature branch should be created off of the `development` branch. It should be named using the format: `feature\your-feature-name`.
2. Once feature branch changes are completed it should be merged into the `development` branch.
3. Two days before the end of the sprint the `development` branch is merged into the `working` branch.
4. After QA approves features from the `working` branch it is merged into the `staging` branch.
5. Production pushes are done on Tuesdays at 5:00 PM EST, so the Tuesday after the client signs off on the `staging` version it can be merged into the `master` branch. 