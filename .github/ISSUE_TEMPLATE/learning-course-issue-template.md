---
name: Learning course issue template
about: Describe this issue template's purpose here.
title: 'feat: learning course notes - {YOUR-NAME}'
labels: learning course
assignees: hbraswelrh

---

## Key Takeaways & Notes


###  Step 1:  Read the docs 

#### Notes
- CaC = 0-toleraance policy for redundancies in developing security content. OpenControl-inspired YAML formatting. Automatically generates SCAP, Ansible Playbooks, and Bash fix scripts. Evaluate and remediate. Standardized reporting and evidence provisioning. Centralized Security Identifiers are sourced from the rules files. Rule definitions for Linux systems are under the linux_os/guide directory. Rule definitions are written as YAML files (rule.yml) and the parent directory is the respective rule's ID.
     - Macros: use "{}" so that Ansible content can use the regular jinja2 macros without interfering with the build system. Macros allow content authors to avoid writing complex directives s.a. variable substitution in rules or remediations, and they can also prevent copy-pasting of the code anywhere in the content. Macros are defined in various .jinja files
     - Checks can be found in the oval directory. OVAL = Open Vulnerability and Assessment Language.
     - Remediations can be found under bash, ansible, anaconda, and puppet directories, and others. Remediations with the "shared" basename (.sh) can be used with any product.
 
- OSCAL Content
     - OSCAL = Open Security Controls Assessment Language
     - ComplianceAsCode/content = definitive, first-edition cookbook for all things compliance. Foundational approved recipes (compliance rules, policies, benchmarks). Source of truth
     - ComplianceAsCode/oscal-content = specialized companion notebook that is always up-to-date with the First-edition Cookbook, even as the original recipes evolve.
     - GitHub Actions = tireless team of culinary coordinators
     - complyscribe = specialized chef
         - Together, they ensure that any improvements or updates to the recipe, whether in first-edition cookbook or specialized cookbook are synced.
     - GitHub Actions spring into action when you update something in the first-edition cookbook. complyscribe automatically translates and updates the specialized cookbook, and vice versa
     - GitHub Actions are the automated bridge, with complyscribe handling the crucial conversion piece.
     - GitHub Actions automate the collaboration. complyscribe facilitates the specific conversion and synchronization.
     - Workflows:
          - sync-comp: inbound - generates oscal content from CaC --> ComplianceAsCode/content
          - sync-controls: inbound - generates oscal controls from CaC --> "
          - sync-oscal-cac: outbound - syncs oscal updates back to CaC --> "
          - sync-cac-oscal: outbound - syncs cac updates back
     - sync-cac-oscal tranforms content from ComplianceAsCode/content into OSCAL using complyscribe CLI
     - Complyscribe is good for content authoring (simplified OSCAL content creation), standards compliance (ensures adherence to OSCAL specifications), format management (consistent content formatting), and automation-ready (seamless ci/cd integration)
     - The ComplianceAsCode/oscal-content repository is the same concept as your own oscal-content-demo repository
          - This repository will eventually be maintained by compliance managers!
     - How to contribute:
          - Fork: Create a fork of the repository
          - Author/edit: modify oscal content files
          - pull request: open a PR with your changes
          - auto-sync: once merged, sync-oscal-cac workflow triggers automatically
- complyscribe = CLI to help users integrate Compliance-Trestle into ci/cd workflows for managing oscal content
    - autosync: synchronizes Trestle-generated Markdown files into OSCAL JSON files, supporting all top-level models
    - rules-transform: transforms rules defined in YAML to oscal component definition JSON file
    - create compdef: creates a new OSCAL component definition, setting up the workspace for rules-transform and autosync
    - sync-upstreams: syncs and validates OSCAL content from a Git repository to a local Trestle workslpace, with options to include or exclude specific models
    - create ssp: creastes new OSCAL ssp, preparing the workspace for autosync by managing the ssp-index.json file
    - sync-cac-content
    - sync-oscal-content
- complyctl = tool that uses oscal to conduct compliance assessment activities. operates by leveraging a plug-in based architecture for each stage of the compliance lifecycle
    - guides users through compliance assessment process, starting with defining a baseline and creating an OSCAL Assessment Plan which acts as the configuration for its generation and scanning operations
    - complyctl list: lists available compliance frameworks
    - complyctl info <framework-id>: displays detailed info about a specific framework's controls and rules
    - complyctl plan <framework-id>: generates an assessment-plan.json file which can be customized using a config.yml file
    - complyctl generate: generates policy artifacts based on the assessment plan
    - complyctl scan: executes the generated artifacts and produces assessmnt-results.json (and optionally assessment-results.md)
    - also provides detailed documentation for installation, quick start, and sample component definitions; encourages contributions and offers guidelines for contributing, style, and a code of conduct; users can write their own plugins
- CNCF = oss foundation, part of linux foundation, vendor-neutral home for many fast growing os projects
    - OSCAL Compass = sandbox maturity-level CNCF project that provides tools and frameworks for compliance automation and security orchestration
- Compliance Trestle = an ensemble of tools that enable the creation, validation, and governance of documentation artifacts for compliance needs
    - NIST's OSCAL standard data format is levereged to connect the dots between humans and machines, creating a seamless bridge between policy and implementation.
    - maintains and enforces transparency of compliance measures across multiple stakeholders in a developer-friendly environment
    - key benefits: artifact eneration (trestle generated artifacts are leveraged by tools for enforcement, measurement, and reporting of compliance); stakeholder alignment (ensures all parties have consistent, up-to-date compliance information); automated workflows (streamlines compliance processes through automation)
    - management of oscal documentation for editing and manipulation with accountability of schema enforcement; transformation of documents from various formats to oscal; streamlined management with a git env.
- Policy as code: defines, updates, shares, and enforces policies using code, enabling automated compliance and governance across infrastructure
     - core objectives: integration (integrate compliance frameworks and existing policy engines); flexibility (enable usage of heterogeneous policy engines in compliance check operations); community (community-driven plugin extension)
     - key benefits: flexibility in choice of policy engines and compliance frameworks; community driven plugin extension
     - policy = rule, condition, or instruction that governs operations or processes. a set of rules or guidelines for an organization, people, or process to achieve compliance, standards, or consistency
     - focus areas: evidence-based (less discussion of measures, more machine-readable evidence of compliance); automation (common examples include testing automation scripts to ensure defined policies are properly enforced)
     - policy engines
          - kyverno: policy engine for kubernetes resources (use case = kubernetes governance)
          - auditree: gitops tool for evidence collection and verification (use case = cloud services via APIs)
     - compliance-to-policy projects aim to bridge the gap between Compliance as Code and Policy as Code. (CaC = OSCAL, PAC = used by policy validation points (PVP)
     - plugins do policy generation (handling policy names/ids and returning policies) and result processing (handling verdict and reasoning for each policy)
     - C2P generates policies in the native format of Policy Validation Points (PVP) from oscal component definitions, then produces OSCAL assessment Results from native assessment results of PVP
     - C2P can be integrated into continuous compliance pipelines (github actions, tekton pipelines, agile authoring pipelines)
- _Do not use italicized formatting_

###  Step 2:  Practice Communicating using Git and Markdown

#### Notes

- _Insert notes here. REPLACE this content with your notes._
- _Do not use italics_

### {REPLACE_ME} Key Concept 1:

#### Notes:

- _Insert notes here. REPLACE this content with your notes._
- _Do not use italics_

## Related Issues

_Link your Excercise: Read the docs issue here_
_Example Issue -> [HERE](https://github.com/hbraswelrh/creme-brulee/issues/7)_
- Related to Issue #()

## Questions

### Self-Reflection & Next Steps
Much to learn!
 
#### Next Steps

## Resources 
_Add or delete resources while taking notes_

- The [manual_steps.md](https://github.com/hbraswelrh/creme-brulee/blob/main/steps/manual_steps.md) has the content of **Step 1:** Read the docs and **Step 2:** Practice Communicating using Git and Markdown.


> ⭐ This issue should be attached to your [self-assessment](https://docs.google.com/forms/d/e/1FAIpQLScIXyhvuLdCcKqBewFGggM7I38W7JJ-phbBUIdhJCw0Puz_cg/viewform?usp=header)
