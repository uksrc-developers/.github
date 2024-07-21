# UKSRC Developers
The UKSRC Developer organisation is aimed at hosting the repositories of UKSRC work.
___
The UKSRC Developers GitHub oraganisation serves to help facilitate easier sharing and centralisation of codes, 
workflows and packages created by and for the UKSRC. In order achieve the ease of sharing, we have recommended practices
for uploading repositories. The three main types of work we expect to have stored on the repository are: 
- codes/scripts 
- packages 
- workflows 

The guidelines we provide here are to be followed at the latest when the ticket, to which the repository is associated, 
is marked as "ready for acceptance". However, we do strongly recommend initiating a repository with a minimum 
Readme.md file to be described in the **Initial Repository** section. 

In the following sections we will describe how workflow repositories should be treated, initial repository 
recommendations, non workflow repositories, and finish with recommended but optional components.

--- 

# **IMPORTANT:**

___
Prior to initiating or pushing any repository remove:
- Passwords 
  - If any part of a code requires passwords, they should be represented with environment variables, and the actual 
value of those variables should **NOT** be shared on the repository.
- Private ssh keys, 
- **data** 
- local directory paths

We forgo uploading in and output data to have a lower storage requirement of repositories.

## Workflows

For workflow repositories, UKSRC requirements are intentionally being aligned with the 
[SRC_Net Scientific Workload Gitlab](https://gitlab.com/ska-telescope/src/src-workloads) requirements, so that any 
workflow repository that initially lives in the UKSRC developers organisation can easily migrate to the SRCNet 
repository when it is ready to do so. There is only one difference: we require that the definition files of containers
be uploaded, whereas the SRCNet repository lists this as optional data. 

## Initial Repositories

When initiating a new repository, a Readme.md file should be created. This should contain: 
- The purpose of the code in the repository
- Description of the repository and the code in it
- Links to relevant internal work pages
  - e.g. Jira tickets, confluence pages, etc.
- List of main developers and collaborators

These components are there to facilitate understanding how the repository fits into the wider UKSRC efforts, to attempt
to prevent unintentional duplication of efforts happening in parallel when they could be joined together, and to provide
an understanding of what the repository will eventually be.

## Non Workflows

For any repositories that have a release or stable version, meaning that part of the repository is intended to be used 
already, there are additional requirements. 

### Readme.md Files
Readme.md file should contain more information. As with the **Initial Repositories**, the Readme should
contain links to relevant Jira tickets and confluence pages, a list of main developers and collaborators, the purpose
of the repository and a description of the repository and code. As the repository should now be in a state to be usable,
the description of the repository should now include what input data is required for it, and how the output data should 
look. Do **NOT** upload output data files, but if it would be helpful, please upload screenshots of output 
data.

In addition to the expansion of the initial repository requirements, developers should ensure the Readme contains: 
- Component details
  - Description of what the components users can/should interact with
- Description of the In and Outputs the codes require
- An example of how to execute/use the codes in the repository
- Software requirements
  - If a container is required, this should only list the software and libraries not located in the container.
  - If a container is optional, all software and libraries that are only needed in the container should be marked as container only
- Container software compatibility
  - This should list the name of the container that is recommended to use
  - If a custom container is required, the path to the container build file in the repository should be provided
- Hardware requirements 
  - Should include the minimum specifications (CPU core count, RAM, Storage, etc.)
  - if available it should also list the recommended specifications 
- Directory Structure description of the repository. 

These requirements serve multiple purposes. On the developer side, they are there to help onboard future developers that 
may take over working on the repositories. On the user side, they are there to help standardise what is to be expected 
in the Readme of a repository so that a user can find the correct code for their goals.

If external documentation exists for the repository, such as a Pypi page for pip installable python packages, we ask 
that such external documentation be linked in the Readme.

After reading the Readme.md file, users and developers who previously were unfamiliar with the work should know what 
inputs they would need for this code to be used as intended, what the outputs should look like, and they should be able 
to use the repository with minimal difficulties.

#### Future Work
If the repository is still actively being developed, or aims to have future development efforts done to it, we ask that 
any developmental goals be listed and described in the end of the Readme file. If Jira tickets or Confluence pages exist for any of this work, we 
ask that they be linked to.

#### Optional additions
'Nice to have' additions that could be beneficial if provided could contain, but are not limited to:
- Link to Demo video of how to use the repository
- Description of how to use the repository for work that may not have been within the original intention
- Relevant information to Profiling data, when accompanied by an analysis of this data and the performance
- How to use the repository in an automatic fashion, if it was not initially designed to be automatic

### Container Definition Files

For any repository that relies on the use, or recommends the use of containers, such as Docker, Podman or Singularity 
images, we require that **NO** fully built containers/images be uploaded. Instead, the container definition files should be 
provided where possible and links to container repos should be provided if such a container was used. The purpose of this is 
to help developers understand what libraries and software requirements go into a container and to make it easier to 
change the containers when necessary. If a container is required, then the software requirements in the container need
not be listed in the software requirements section of the Readme. If using a container is optional, we ask that the 
software Requirements section of the Readme list all software and libraries, and mark the ones that should be in a 
container.

