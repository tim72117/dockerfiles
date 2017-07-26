FROM python:3

RUN pip3 install --upgrade pip & pip3 install jupyter

RUN useradd -ms /bin/bash jupyter

USER jupyter

RUN jupyter notebook --generate-config

RUN echo "c.NotebookApp.ip = '*'" >> /home/jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.port = 8889" >> /home/jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.password = u'sha1:ac40cc63178b:6a652f41e246a163b771c1c684c13dca01dab31e'" >> /home/jupyter/jupyter_notebook_config.py

EXPOSE 8889

WORKDIR /home/jupyter

CMD ["jupyter", "notebook", "--no-browser"]