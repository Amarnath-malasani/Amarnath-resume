%%%%
% MTecknology's Resume
%%%%
% Author: Michael Lustfield
% License: CC-BY-4
% - https://creativecommons.org/licenses/by/4.0/legalcode.txt
%%%%

\documentclass[letterpaper,10pt]{article}
%%%%%%%%%%%%%%%%%%%%%%%
%% BEGIN_FILE: mteck.sty
%% NOTE: Everything between here and END_FILE can
%% be relocated to "mteck.sty" and then included with:
%\usepackage{mteck}

% Dependencies
% NOTE: Some packages (lastpage, hyperref) require second build!
\usepackage[empty]{fullpage}
\usepackage{titlesec}
\usepackage{enumitem}
\usepackage[hidelinks]{hyperref}
\usepackage{fancyhdr}
\usepackage{fontawesome5}
\usepackage{multicol}
\usepackage{bookmark}
\usepackage{lastpage}

% Sans-Serif
%\usepackage[sfdefault]{FiraSans}
%\usepackage[sfdefault]{roboto}
%\usepackage[sfdefault]{noto-sans}
%\usepackage[default]{sourcesanspro}

% Serif
\usepackage{CormorantGaramond}
\usepackage{charter}

% Colors
% Use with \color{Name}
% Can wrap entire heading with {\color{accent} [...] }
\usepackage{xcolor}
\definecolor{accentTitle}{HTML}{0e6e55}
\definecolor{accentText}{HTML}{0e6e55}
\definecolor{accentLine}{HTML}{a16f0b}

% Misc. Options
\pagestyle{fancy}
\fancyhf{}
\fancyfoot{}
\renewcommand{\headrulewidth}{0pt}
\renewcommand{\footrulewidth}{0pt}
\urlstyle{same}

% Adjust Margins
\addtolength{\oddsidemargin}{-0.7in}
\addtolength{\evensidemargin}{-0.5in}
\addtolength{\textwidth}{1.19in}
\addtolength{\topmargin}{-0.7in}
\addtolength{\textheight}{1.4in}

\setlength{\multicolsep}{-3.0pt}
\setlength{\columnsep}{-1pt}
\setlength{\tabcolsep}{0pt}
\setlength{\footskip}{3.7pt}
\raggedbottom
\raggedright

% ATS Readability
\input{glyphtounicode}
\pdfgentounicode=1

%-----------------%
% Custom Commands %
%-----------------%

% Centered title along with subtitle between HR
% Usage: \documentTitle{Name}{Details}
\newcommand{\documentTitle}[2]{
  \begin{center}
    {\Huge\color{accentTitle} #1}
    \vspace{10pt}
    {\color{accentLine} \hrule}
    \vspace{2pt}
    %{\footnotesize\color{accentTitle} #2}
    \footnotesize{#2}
    \vspace{2pt}
    {\color{accentLine} \hrule}
  \end{center}
}

% Create a footer with correct padding
% Usage: \documentFooter{\thepage of X}
\newcommand{\documentFooter}[1]{
  \setlength{\footskip}{10.25pt}
  \fancyfoot[C]{\footnotesize #1}
}

% Simple wrapper to set up page numbering
% Usage: \numberedPages
% WARNING: Must run pdflatex twice!
\newcommand{\numberedPages}{
  \documentFooter{\thepage/\pageref{LastPage}}
}

% Section heading with horizontal rule
% Usage: \section{Title}
\titleformat{\section}{
  \vspace{-5pt}
  \color{accentText}
  \raggedright\large\bfseries
}{}{0em}{}[\color{accentLine}\titlerule]

% Section heading with separator and content on same line
% Usage: \tinysection{Title}
\newcommand{\tinysection}[1]{
  \phantomsection
  \addcontentsline{toc}{section}{#1}
  {\large{\bfseries\color{accentText}#1} {\color{accentLine} |}}
}

% Indented line with arguments left/right aligned in document
% Usage: \heading{Left}{Right}
\newcommand{\heading}[2]{
  \hspace{10pt}#1\hfill#2\\
}

% Adds \textbf to \heading
\newcommand{\headingBf}[2]{
  \heading{\textbf{#1}}{\textbf{#2}}
}

% Adds \textit to \heading
\newcommand{\headingIt}[2]{
  \heading{\textit{#1}}{\textit{#2}}
}

% Template for itemized lists
% Usage: \begin{resume_list} [items] \end{resume_list}
\newenvironment{resume_list}{
  \vspace{-7pt}
  \begin{itemize}[itemsep=-2px, parsep=1pt, leftmargin=30pt]
}{
  \end{itemize}
  %\vspace{-2pt}
}

% Formats an item to use as an itemized title
% Usage: \itemTitle{Title}
\newcommand{\itemTitle}[1]{
  \item[] \underline{#1}\vspace{4pt}
}

% Bullets used in itemized lists
\renewcommand\labelitemi{--}

%% END_FILE: mteck.sty
%%%%%%%%%%%%%%%%%%%%%%


%===================%
% John Doe's Resume %
%===================%

%\numberedPages % NOTE: lastpage requires a second build
%\documentFooter{\thepage of 2} % Does similar without using lastpage
\begin{document}

  %---------%
  % Heading %
  %---------%

  \documentTitle{Venkata Amarnath Malasani}{
    % Web Version
    %\raisebox{-0.05\height} \faPhone\ [redacted - web copy] ~
    %\raisebox{-0.15\height} \faEnvelope\ [redacted - web copy] ~
    %%
    \href{tel:1234567890}{
      \raisebox{-0.05\height} \faPhone\ +91 7975215709} ~ | ~
    \href{mailto:user@domain.tld}{
      \raisebox{-0.15\height} \faEnvelope\ amarnathmalasani10@gmail.com} ~ | ~
    \href{https://www.linkedin.com/in/mv-amarnath/}{
     \raisebox{-0.15\height} \faLinkedin\ linkedin.com/in/mv-amarnath} 
    %\href{https://github.com/USER}{
     % \raisebox{-0.15\height} \faGithub\ github.com/USER}
  }

  %---------%
  % Summary %
  %---------%

  \tinysection{Summary}
AWS DevOps Engineer with 3.2 years of experience in designing, building, and maintaining scalable and reliable systems. Proficient in covering the entire software product life cycle, including CI/CD, scripting, and enhancing outdated workflows through automation and environment setup for builds and deployments.

  %--------%
%Skills%
  %--------%

  \section{Skills}

  \begin{multicols}{2}
    \begin{itemize}[itemsep=-2px, parsep=1pt, leftmargin=75pt]
      \item[\textbf{Version Control :}] Git, GitHub
      \item[\textbf{Build Tools :}] Maven
      \item[\textbf{Cloud :}] AWS
      \item[\textbf{Scripting :}] Python
      \item[\textbf{CI/CD :}] Jenkins
      \item[\textbf{IAC Tool :}] Terraform, Ansible
      \item[\textbf{GitOps Tool :}] ArgoCD
      \item[\textbf{Containerization and Orchestration :}] Docker, Kubernetes
      \item[\textbf{Docker Registry :}] AWS ECR, Docker Hub
      \item[\textbf{Monitoring and Alerting :}] Prometheus, Grafana and  Cloud Watch
    \item[\textbf{Artifactory Repository :}] Nexus Repository
    \item[\textbf{Static Code Analysis Tool :}] SonarQube
    \end{itemize}
  \end{multicols}

  %------------%
  % Experience %
  %------------%

  \section{Experience}

  \headingBf{Wissen Infotech}{Aug 2022 -- Sep 2024}
  \headingIt{DevOps Engineer}{}
  
  \begin{resume_list}


    \item Involved in CI/CD process and integrated \textbf {GIT, Nexus Repository, SonarQube, Maven artifacts} build with \textbf  {Jenkins} and creating \textbf {Docker image} and using the Docker image to deploy over \textbf {AWS EKS} (Kubernetes).
\item Worked with \textbf{GIT} to manage source code repositories and performed branching, merging, and tagging depending on requirements. 
\item Performed continuous Build and Deployments to multiple \textbf {DEV, QA, PRE-Prod} and \textbf {PROD} environments.
\item Integrated \textbf {SonarQube} with Jenkins for continuous inspection of code quality and analysis with \textbf {SonarQube scanner} for Maven.
\item Integrated \textbf {Nexus Repository} with Jenkins to Store Artifact’s
\item Experience with container-based deployments using Docker and storing docker images securely in \textbf {AWS ECR} and \textbf {Docker Hub}.
\item  Identify, troubleshoot and resolve issues related to the build and deploy process.
\item  Deploying Docker images on \textbf {Kubernetes cluster} using \textbf {Helm charts} and exposing the application to internet using \textbf {Ingress Object}.
\item Experience Creating and Managing Pods, Deployment, Services, DaemonSet, Job, Cron Job Using Kubernetes Manifest files
\item  Implemented \textbf {GitOps} with \textbf {Argo CD} for automated application deployments.
\item  Configure and manage \textbf {Prometheus} and \textbf {Grafana} for alerting and monitoring system metrics. 
\item Implemented centralized logging and log analysis using \textbf {EFK} (Elasticsearch, Fluentd, and Kibana) Stack, improving troubleshooting and monitoring capabilities. \item Implemented infrastructure automation using \textbf {Terraform} reducing manual provisioning time by 70 percent and improving consistency across environments.
\item Written the \textbf  {Ansible} YAML Scripts to Configure the remote servers.
\item Developed \textbf {Bash scripts} to automate system administration tasks.
\item Hands-on experience in provisioning databases using \textbf{RDS} (MySQL and Aurora) and managing clusters in AWS ECS, including task definitions and service creation using Terraform
\item Managed and configured infrastructure on AWS Cloud services like \textbf {AWS IAM, VPC, EC2, EKS, EBS, S3, ELB, Auto Scaling, Route 53, Cloud Front, Cloud Watch, Cloud Trail, AWS RDS, AWS DynamoDB} and \textbf {SNS}.
    \item Experienced in creating complex \textbf { IAM }policies, Roles and user management for delegated access within AWS.
\item Experienced in creating various dashboards, metrics, alarms and notifications for servers using \textbf { AWS Cloud Watch}.
\item Creating \textbf { S3 bucket} and adding lifecycle policy for the buckets, Enabling Versioning for protecting buckets from automatic termination.
\item Hands on experience in configuration of SNS topics for alerts received from Cloud Watch.

 
  \end{resume_list}
  \headingBf{Tata Consultancy Services (TCS)}{Aug 2021 -- July 2022}
  \headingIt{Junior DevOps Engineer}{}
  
  \begin{resume_list}
  \itemTitle{Payroll Company: Proxytem software services }
  
\item Administration of \textbf{GitHub} includes creating branches, tagging, merging and access permissions.
\item Developing and maintaining the continuous integration and deployment pipelines using \textbf{GIT, JENKINS, MAVEN, DOCKER, ANSIBLE, SONARQUBE} and \textbf{Nexus Repository}.
\item Manually deployed war, jar files to various environments as part of the release process.
  \item Working experience on pipeline and mutlibranch pipeline for our services in development, staging, and pre-production environments by using the integrated tools \textbf{Jenkins}.
  \item Experience with Spring Boot framework for developing Java-based microservices.
  \item Collaborated with developers to optimize code repositories, resulting in faster code retrieval and collaboration.
  \item Designed, implemented, and managed \textbf{AWS} infrastructure using \textbf{Terraform} for both existing and new services.
  \item Deploy and manage services such as \textbf{EC2 Windows VMs, VPC, DNS, and ALB}.

  \item Build and optimize container images and \textbf{Dockerfiles} for application deployment.
\item Implement security best practices and conduct vulnerability scanning using tools like \textbf{SonarQube}.

\item Developed shell scripts for automating node health checks, monitoring CPU, memory, and other critical metrics, and ensuring system stability.

   


  %-----------%
  % Education %
  %-----------%

  \section{Education}

  \headingBf{SRI VENKATESWARA UNIVERSITY}{2018 -- 2021} % Note: Adding year(s) exposes an implied age
  \headingIt{Bachelor of Science in Computer Science}{}
  \headingIt{}{}

\section{Certifications}
\headingBf {AWS Certified Cloud Practitioner}{2023 -- 2026}


\end{document}
