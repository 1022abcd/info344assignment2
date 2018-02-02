# info344assignment2
# INFO 344 PA 2

## Website Link
[http://achocloudservice.cloudapp.net/SearchPage.html](https://www.google.com)

## Screenshot
![alt text](./AzureScreentshot.png "Screenshot of running instance")

## Write up

1) Data File
    -Download the data file from the wikipedia page.
2) Microsoft Azure Storage explorer
    -Download the Azure Storage explorer 
    -Connect to Azure Storage
    -Use a storage account name and key
    -Go to 'Storage Account' -> 'name(external)' -> 'Blob Container'
    -Right click the 'Blob Container' and 'Create Blob Container'
    -Upload the wiki data file in the blob container just created

3) Coding
    'TrieNode.cs'
        -Simple basic node object 
    'TrieTree.cs'
        -Creating a Trie-tree structure using TrieNode
        -Does two functions
            Insert 
                :pass until the end of the node if the word is stored in each node
                :add chars in each trie node using recursion
                :when the last char is added, endOfWord = true;
            Search
                :pass until the end of the node that has the last char of the given input
                :set the condition to be returning result <= 10
                :recursively addes the word in a list when reaching the node with endOfWord = true;
    'PA2.asmx'
        -There are 3 methods 
            DownloadBlob()
                ~Downloads the blob from the azure storage using storage 
                connection string and the container reference.
            BuildTrie() 
                ~Using regex to filter out for post-processing
                ~Parse each line in the downloaded blob file and 
                send those lines to the TrieTree.insert(string word) method 
            SearchTrie(String word)
                ~Sends the word to the TrieTree.search(string word) method
    'SearchPage.html'
        -Using AJAX to pull out the suggestion data from PA2.asmx/searchTrie
        -Every key stroke user makes, the ajax function gives the relevant search suggestion.

4) Test
    -Download the blob
    -BuldTrie
    -SearchTrie with string
    -SearchPage.html and try

5) Things should be fixed
    -Memory Issue
    -Ping the server every 6 hours.
