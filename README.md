# Compression-of-file-by-Huffman-Coding
import os
import eheapq
import mysignals as sigs
def make_freq_dict(self,text):
    freq={}
    for char in text:
        if not char in freq:
            freq[char]=0
        freq[char]+=1
    return freq
def make_heap(self,freq):
    for key in freq:
        node=self.heapnode(key,freq[key])
        heapq.heappush(self.heap,node)
def merge_code(self):
    while(len(self.heap)>1):
        node1=heapq.heappop(self.heap)
        node2=heapq.heappop(self.heap)
        merged=heapnode(node,node1_freq+node2_freq)
        merged.left=node1
        merged.right=node2
        heapq.heappush(self.heap,merged)
def make_code(self):
    root=heapq.heappop(self.heap)
    current_code=" "
    self.make_code(root,current_code)
def get_encoded_code(self,text):
    encoded_text=" "
    for char in text:
        encoded_text+= self.code[char]
    return encoded_text
def pad_encoded_text(self,encoded_text):
    extra_padding=8 - len(encoded_text)%8
    for i in range(extra_padding):
        encoded_text+="0"
    padded_info="{0:08b}".format(extra_padding)
    encoded_text=padded_info+encoded_text
    return encoded_text
def get_byte_array(self,padded_encoded_text):
    if(len(padded_encoded_text)%8!=0):
        print("encoded text not padded properly")
        exit(0)
        b=bytearray()
        for i in range(0,len(padded_encoded_text),8):
            byte=padded_encoded-text[i:i+8]
            b.append (int(byte,2))
            return b
def compress(self):
    sigs,file_extention=os.path.splitext(self.path)
    output_path= sigs + ".bin"
    with open(self.path,'r') as file, open (output_path, 'wb') as output:
         text=file.read()
         text=text.rstrip()
         freq=self.make_freq_dict(text)
         self.make_heap(freq)
         self.make_code()
         encoded_text=self.get_encoded.text(text)
         padded_encoded_text=self.pad_encoded_text(encoded_text)
         b=self.get_byte_array(padded_encoded_text)
         output.write(byte(b))
         print("compressed")
    return output_path

