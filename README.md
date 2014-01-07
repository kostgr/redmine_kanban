# Redmine Kanban Plugin

The Redmine Kanban plugin is used to manage issues according to the Kanban
system of project management.

## Features

  * Global Kanban page showing the status of issues across projects
  * Multiple "Panes" to show the lifecycle of an issue
      * Incoming Pane
      * Unstaffed Backlog pane
      * Quick Tasks pane - issues without a time estimate
      * Selected Tasks - Manager prioritized list
      * Active Staffed Requests - issues in progress
      * Testing Staffed Requests - issues awaiting testing
      * Finished Requests
  * Updates to Kanban view are saved to the issues
      * Issue status
      * Issue assignment
      * Issue start date

## Installation and Setup

 1. Install the aasm and block_helpers gems: `sudo gem install aasm
    block_helpers`
 2. Follow the normal Redmine plugin installation steps (see
    http://www.redmine.org/wiki/redmine/Plugins)
 3. Run the plugin migrations: `rake db:migrate_plugins`
 4. Restart your Redmine web servers (e.g. mongrel, thin, mod_rails)
 5. Login and configure the plugin (Administration > Plugins > Configure). See
    below for the recommended approach.
 6. Click the Kanban link in the top left menu

## Usage

### Recommended configuration

The Kanban plugin uses 7 sets of lists, referred to panes:

  * Incoming - New
  * Unstaffed Backlog - Approved
  * Quick Tasks
  * Selected Tasks - Selected
  * Active Staffed Requests - In Progress
  * Testing Staffed Requests - Resolved
  * Finished Requests - Complete

Each pane (except Quick Tasks) needs to be associated with a Issue Status. The
recommended statuses are above but you can customize them as needed. The
Staffed panes (Active, Testing, Finished) also require choosing a Role to use.
Any user with this Role will have their own personal set of panes created on
the Kanban page.

Quick tasks will pull in the highest priority issues from the Backlog that
don't have an estimate. This is useful when someone has a limited amount of
time but wants to finish something, like when it's 4:30pm on a Friday
afternoon.

## License

This plugin is licensed under the GNU GPL v2. See COPYRIGHT.txt and GPL.txt for
details.
