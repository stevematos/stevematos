```python
from pydantic import BaseModel
from typing import List, Optional, Dict


class SoftwareDeveloper(BaseModel):
    username: str
    name: str
    position: str
    linkedin: Optional[str] = None
    code: Dict[str, List[str]]
    architecture: List[str]

    def __str__(self) -> str:
        return self.__repr_str__('\n')


me_data = {
    'username': 'stevematos',
    'name': 'Steve Matos',
    'position': 'Python Software Developer',
    'linkedin': 'https://www.linkedin.com/in/steve-matos/',
    'code': {
        'backend': ['Python', 'Flask', 'Django', 'FastAPI', 'Odoo'],
        'database': ['PostgreSQL', 'MySQL', 'Oracle', 'SQL Server', 'SQLite3', 'Redis'],
        'devops': ['Docker', 'Linux', 'AWS'],
        'frontend': ['HTML', 'CSS', 'JavaScript', 'ReactJS', 'Svelte', 'Boostrap'],
        'tools': ['GIT', 'GitHub', 'GitLab', 'Pandas', 'SQLAlchemy', 'Celery'],
        'misc': ['TDD', 'SCRUM', 'gRPC']
    },
    'architecture': ['MVC', 'SOAP', 'Serverless', 'microservices']
}

if __name__ == '__main__':
    stevematos = SoftwareDeveloper(**me_data)
    print(stevematos)

""" 
    username = 'stevematos'
    name = 'Steve Matos'
    position = 'Python Software Developer'
    linkedin = 'https://www.linkedin.com/in/steve-matos/'
    code = {'backend': ['Python', 'Flask', 'Django', 'FastAPI', 'Odoo'],
            'database': ['PostgreSQL', 'MySQL', 'Oracle', 'SQL Server', 'SQLite3', 'Redis'],
            'devops': ['Docker', 'Linux', 'AWS'],
            'frontend': ['HTML', 'CSS', 'JavaScript', 'ReactJS', 'Svelte', 'Boostrap'],
            'tools': ['GIT', 'GitHub', 'GitLab', 'Pandas', 'SQLAlchemy', 'Celery'], 'misc': ['TDD', 'SCRUM', 'gRPC']}
    architecture = ['MVC', 'SOAP', 'Serverless', 'microservices']
"""

```