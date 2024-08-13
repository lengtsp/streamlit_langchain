cd "/root/mycode/streamlit1"
conda create -n streamlit_langchain Python=3.10
conda activate streamlit_langchain

pip install -r requirements.txt

streamlit run app.py --server.port=8501 --server.address=0.0.0.0

#build image
docker build -t streamlit/langchain1 -f Dockerfile .

#build container
docker run -p 8501:8501 streamlit/langchain1
