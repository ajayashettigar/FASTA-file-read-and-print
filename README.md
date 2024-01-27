# FASTA-file-read-and-print
This is a code in python that can download any FASTA files by taking input url of that file.
# Code
# import these packages
import requests
from Bio import SeqIO
# define the function
def readfile(link):
    req=requests.get(link)
    filename=req.url[link.rfind('/')+1:]
    s=[]
    for Seq in SeqIO.parse("ls_orchid.fasta.txt", "fasta"):
        s.append(str(Seq))
        #print the id
        print(f"FASTA indentifier:\n {Seq.id}\n")
        #print the sequence
        print(f"Sequence:\n {Seq.seq}\n")
        #print the length of sequence
        print(f"Lenght of this file is {len(Seq)}")
link=input("Paste the url:\n")
readfile(link)
