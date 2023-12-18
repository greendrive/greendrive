# Embedding Retrieval with Chroma on GreenDrive
GreenDrive offers a straightforward method for utilizing Chroma to store and retrieve data through embeddings. 

## Setup
You can download and install (or update to) the latest release of Chromadb with the following command in your terminal 
```shell
pip3 install -Uq chromadb numpy datasets tqdm ipywidgets
```

## Example Dataset
In this demo, we use the [SciQ dataset](https://arxiv.org/abs/1707.06209), available from [HuggingFace](https://huggingface.co/datasets/sciq). You can download it and save it on your local computer. In this demo, we use Mac and save it as the format **/path/to/save/to**.

## Loading the data into Chroma
We will demonstrate how to load the data based on a Chroma official demo, with some code adjustments to accommodate GreenDrive.

```python
from datasets import load_dataset
import chromadb

# Change /path/to/save/to according to your actual path
client = chromadb.PersistentClient(path="/path/to/save/to")
 
dataset = load_dataset("sciq", split="train")

# Filter the dataset to only include questions with a support
dataset = dataset.filter(lambda x: x["support"] != "")

print("Number of questions with support: ", len(dataset))
 
collection = client.get_or_create_collection(name="sciq_supports")
batch_size = 1000
for i in range(0, len(dataset), batch_size):
     collection.add(
         ids=[
             str(i) for i in range(i, min(i + batch_size, len(dataset)))
         ],  # IDs are just strings
         documents=dataset["support"][i : i + batch_size],
         metadatas=[
             {"type": "support"} for _ in range(i, min(i + batch_size, len(dataset)))
         ],
     )
```

Create a Private Database on GreenDrive
1. In GreenDrive, click **Vector Dataset** on the left
2. Select **Create**
3. Enter the name of the folder
4. Enter the actual folder path on your computer as the format **/path/to/save/to**
5. Click OK

![image](https://github.com/greendrive/greendrive/assets/150257109/416c7660-138c-4583-bc09-ec6250e42d37)

When the status changes to **Replicating**, it indicates that the fold was created successfully and is replicating.

![image](https://github.com/greendrive/greendrive/assets/150257109/ea9019cc-8348-46d6-838f-5d65172ed7f6)

## Stop and continue to replicate
To stop synchronization, click the checkbox to choose the folder.
Click **Stop Sync**

![image](https://github.com/greendrive/greendrive/assets/150257109/901c41e7-1690-4717-bb68-8557dfeed0ff)

When the status changes to **None**, it indicates the synchronization has stopped.

![image](https://github.com/greendrive/greendrive/assets/150257109/99477982-65b2-41dc-9a51-6ea26712ce40)

If you need to continue to synchronize,
1. Click the folder
2. Click **Create**
3. Turn on **Sync**
4. Input your folder path

![image](https://github.com/greendrive/greendrive/assets/150257109/0101d415-7eab-4731-adaa-62ac637664be)

When the status changes to **Replicating**, it indicates that the synchronization process has been restarted.

## Restore database
Once the data is loaded successfully, you can use GreenDrive to restore it on another device.
Choose the folder
Click **Restore**

![image](https://github.com/greendrive/greendrive/assets/150257109/189bce87-a062-49ea-adba-c6a0d37083c0)

Choose or create a folder
Click **Open**

After the above steps,  the Status changes to **Restoring**.

![image](https://github.com/greendrive/greendrive/assets/150257109/239b776a-60a5-4c41-bb33-0182a159ab38)

## Query the data
Querying the data in this demo is also based on the [Chroma demo](https://github.com/chroma-core/chroma/blob/main/examples/basic_functionality/start_here.ipynb). Remember to change the part  "/path/to/save/to" into your actual path.

```python
from datasets import load_dataset
import chromadb
# Change /path/to/save/to according to your actual path
client = chromadb.PersistentClient(path="/path/to/save/to")
 
dataset = load_dataset("sciq", split="train")

collection = client.get_collection("sciq_supports")
results = collection.query(
    query_texts=dataset["question"][:10],
    n_results=1)

# Print the question and the corresponding support
for i, q in enumerate(dataset['question'][:10]):
    print(f"Question: {q}")
    print(f"Retrieved support: {results['documents'][i][0]}")
    print()
```

You will get the query questions along with their retrieved supports after running the above code in your terminal.
