This is a SQuaRE Technical Note describing the implementation of the
LSST Publication Board process in JIRA.

Policy
======

The governing policy is http://ls.st/LPM-162 - this document is only
an implementation specification for the workflow of the publication
board.

Workflow
========

The following workflow statuses are available. By request, the workflow
is not constrained, i.e. one can transition from and to any status from
any other status.

Note that we use the words "paper" and "journal" for the thing that is
submitted and its eventual publication destination, by convention and
because they are expected to dominate usage, but these are general
terms for "artifact that is subject to the PubBoard" and "eventual
publication outlet".

Here is the Kanban board view of the statuses allowed by the workflow:

.. image:: _static/kanban.png
   :alt: Kanban board listing status steps

A definition of those steps follows.

Todo statuses
-------------

This is the status (aka New) that a newly created story has.

Proposed
    A paper (or other artifact) has been submitted to the PubBoard

In Progress statuses (PubBoard)
-------------------------------

With PubBoard
    Awaiting Action from the PubBoard (referee assignment, approval etc)
With Reviewer
    The paper is with the reviewer assigned by the pub board
With Author
    The paper is with the author (eg. for edits)
With Project
    The paper is in its project-wide consultation period

Depending on the extent of comments received, a paper may transition
several times between these statuses. For example it may bounce between
the author and reviewer several times as comments are made and
addressed.


Done Statuses - Pub Board
-------------------------

Approved
    The paper has been approved by the PubBoard for publication

Rejected
    The paper has failed to clear the PubBoard process


Done statuses (Journals)
------------------------

The following statuses can be used to track the paper after it has
exited the PubBoard process if the author, LSST Communications or LSST
subsystem cares to do so. However, they are non-actionable statuses by
the PubBoard and therefore JIRA treats them as resolved.

Journal Submitted
    The paper has been submitted to the journal (or proceedings etc.)
Journal In Review
    The paper is in the journal's peer review process
Journal In Press
    The paper has been accepted and has a publication reference


Issue Types
===========

The PubBoard has the following Issue Type:

Paper
    An artifact subject to PubBoard publication policy



Supported Fields
================

In general the reporter of the ticket is the person dealing with the
PubBoard (typically the lead author) and the description field serves
as an abstract. The assignee is as with code review, the person
assigned for internal evaluation of the paper. The assignee will change
as the paper moves through the review process.

The following fields are standard JIRA fields used by the PUB project:

Summary
    Title of the submission.

Component
    Subsystem most relevant for the submission. This will control
    who gets notified to begin the review process and allow related papers
    to easily be queried by the subsystem manager. Most of the components
    directly relate to a corresponding project subsystem. Use "Other or N/A"
    for cross-subsystem papers and use "Science Performance" for papers
    relating to the scientific performance of the telescope system including
    simulations.

Assignee
    Person assigned to handle the submission. This can be left in its
    default state for automatic assignment to the component lead or it
    can be used to suggest a reviewer.

Watchers
    People who would like to follow the discussion.
    Co-authors could be added here.

Description
    The abstract of the submission and any other narrative information
    that is deemed to be relevant.

Attachment
    This is where to upload the PDF of the submission.

Due Date
    Date, if relevant, by which the paper must be submitted.
    This is usually relevant for conference submissions and provides
    the Publication Board with some idea of the urgency of the review.
    Supporting information can be added to the Description field.

The following issue fields are introduced or have special meaning for
PubBoard stories:

Bibcode
    Lookup reference to citable entry (typically ADS or a DOI).
    Added after the publication has been submitted for publication.

Peer-reviewed
    Whether this counts as a peer-reviewed publication for our metrics.


Swimlanes
=========

Swimlanes have been configured to display per assignee, and
unassigned. This should help figure out if any particular reviewer is
a bottleneck.


Links
=====

- `JIRA Pub Board project <https://jira.lsstcorp.org/secure/RapidBoard.jspa?rapidView=92&projectKey=PUB>`_

  The JIRA Project described in this note

- `SQR-005: Publication Board JIRA Project - User Note <https://sqr-005.lsst.io>`_

  Online version of this document

- `github.com/lsst-sqre/sqr-005 <https://github.com/lsst-sqre/sqr-005>`_

  The source repository for this note. PR corrections/additions.
