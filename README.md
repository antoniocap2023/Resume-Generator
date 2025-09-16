# Resume Generator

<div align="center">

![Resume Generator Banner](https://via.placeholder.com/800x200/2E86AB/FFFFFF?text=Resume+Generator+%7C+University+of+Michigan+ITS)

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/your-username/Resume_Generator_API)
[![Version](https://img.shields.io/badge/version-1.0.0-blue)](https://github.com/your-username/Resume_Generator_API)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)
[![Django](https://img.shields.io/badge/Django-4.2+-092E20?logo=django)](https://djangoproject.com/)
[![React](https://img.shields.io/badge/React-18+-61DAFB?logo=react)](https://reactjs.org/)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python)](https://python.org/)

*Automated resume and cover letter generation tool developed for University of Michigan Information Technology Services testing workflows*

</div>



## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [File Format Requirements](#file-format-requirements)
- [API Documentation](#api-documentation)
- [Frequently Asked Questions](#frequently-asked-questions)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)


## Overview

The **Resume Generator** is a full-stack web application designed for the University of Michigan Information Technology Services (ITS) to automate the generation of resumes and cover letters for testing purposes. Built with **Django Ninja** (backend) and **React** (frontend), this tool streamlines the creation of multiple resume variations based on job requirements and customizable templates.

### Why This Tool Exists

- **Automated Testing**: Generate multiple resume variations for ITS testing workflows
- **Efficiency**: Batch process resume and cover letter generation
- **Consistency**: Ensure standardized formatting across all generated documents
- **Flexibility**: Support multiple templates and customizable generation orders



## Features

**Batch Resume Generation**: Create multiple resumes and cover letters simultaneously  

**ZIP File Export**: Download all generated documents in a single archive  
**Multiple Templates**: Choose from various professional resume templates  
**Customizable Order**: Generate resumes before cover letters or vice versa  
**Random Generation**: Automatically randomize templates and generation order  
**Structured Input**: Support for organized text file inputs with clear formatting  
**OpenAI Integration**: Leverage AI for intelligent content generation  
**Real-time Processing**: Fast generation with live progress updates  


## Architecture
```mermaid
graph TD
    A[React Frontend] -->|HTTP Requests| B[Django Ninja API]
    B -->|File Processing| C[File Parser]
    B -->|AI Generation| D[OpenAI API]
    C -->|Parsed Data| E[Resume Generator Engine]
    D -->|Generated Content| E
    E -->|Templates| F[Template Engine]
    F -->|Formatted Documents| G[ZIP Generator]
    G -->|Download| A
    
    subgraph "Frontend Layer"
        A
        H[File Upload Interface]
        I[Configuration Panel]
        J[Download Manager]
    end
    
    subgraph "Backend Layer"
        B
        C
        E
        F
        G
    end
    
    subgraph "External Services"
        D
    end

