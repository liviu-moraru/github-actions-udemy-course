- [Academind Community on Discord](https://academind.com/community)
- [Resurse pe GitHub](https://github.com/academind/github-actions-course-resources)
  
  # Sectiunea 3 Basic Building Blocks & Components

  ## Parti constitutive:
  - Workflows
  - Jobs
  - Steps
  
  Relatia dintre ele:
  De un Repository se ataseaza unul sau mai nulte Workflows
  
  Un workflow contine unul sau mai multe joburi.
  
  Fiecare job contine unul sau mai multe steps.
  
  Un workflow e activat de un *event*

  Un job defineste un Runner (execution environment)

  Joburile care formeaza un workflow, ruleaza in paralel (default) sau secvential. Pot exista conditii pt. rularea unui job.

  Step-ul executa un shell script sau un Action (preconfigurate sau custom).

  Step-urile ruleaza secvential in interiorul unui job. Pot exista conditii pt. rularea unui step.

  ## Disponibilitate si preturi

  - Pt. repositoriile publice, serviciul GitHub Actions este gratuit.
  - Pt. cele private este o [cota lunara](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions).
  
  
  ## Primul workflow

```yaml
name: First Workflow
on: workflow_dispatch
jobs:
  first-job:
    runs-on: ubuntu-latest
    steps:
      - name: Print greeting
        run: echo "Hello World!"
      - name: Print goodbye
        run: echo "Done - bye!"
```

Tradus in json:

```
{
    "name": "First Workflow",
    "on": "workflow_dispatch",
    "jobs": {
        "first-job": {
            "runs-on": "ubuntu-latest",
            "steps": [
                {
                    "name": "Print greeting",
                    "run": "echo \"Hello World!\""
                },
                {
                    "name": "Print goodbye",
                    "run": "echo \"Done - bye!\""
                }
            ]
        }
    }
}
```




