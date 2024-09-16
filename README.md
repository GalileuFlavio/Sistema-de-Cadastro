# Sistema-de-Cadastro
Sistema de Cadastro de Funcionários

from sqlalchemy import create_engine, Column, Integer, String, Float, Date
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker

engine = create_engine('sqlite:///empresa.db')
Base = declarative_base()

class Funcionario(Base):
    __tablename__ = 'funcionarios'
    id = Column(Integer, primary_key=True)
    nome = Column(String)
    cargo = Column(String)
    data_admissao = Column(Date)
    salario = Column(Float)

Base.metadata.create_all(engine)
Session = sessionmaker(bind=engine)
session = Session()
