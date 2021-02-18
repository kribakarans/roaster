**1. Added node in sorted list**
```

typedef struct node {
	struct node *next;
	int data;
} node_t;


node_t *add_node(node_t *head, int data)
{
	node_t *new = NULL;
	node_t *ptr = NULL;

	new = malloc(sizeof *node);
	if (new == NULL) {
		perror("malloc failed");
		return NULL;
	}

	new->next = NULL;
	new->data = data;

	if (head == NULL) {
		head = new;
		return head;
	}


	ptr = head;

	while(ptr != NULL) {
		if (new->data > ptr->data) {
			ptr->next = new;
		} else if () {
			
		}

	}

}
```
**2. Reversing doubly linked list**
```
typedef struct node {
	struct node *next;
	int data;
} node_t;

int reverse(node_t *head)
{
	node_t *ptr = NULL;

	if (head == NULL) {
		return -1;
	}

	ptr = head;	

	while(ptr != NULL) {
		if (ptr->next != NULL) {
			next = ptr->next;
			prev = ptr->prev;
			ptr->next = prev;
			ptr->prev = next;
		}
		ptr = next
	}
}
```
**3. What is dangling pointer?**
```

int a;
static int b;

int main()
{
	static int c;
	char *ptr = (char *)malloc(10);

	free(ptr);

	ptr ///
}
```

what if dest mac is not match in switch and router ?<br>
fragmentation in ip stack ?<br>
what if frame exceeds the mtu size ?<br>
	if fragmentation enable, the frame get fragment<br>
max port no ?<br>
can we set own client port no ?<br>
what listen will do ?<br>
	monitor incomming req and create passive sockets<br>
How global values are acceseddd in parent and child ?<br>
how mutex values in acccess by two process (bcz two procs are not communicate) ?<br>
is static varible with same name is cause compilation error ?<br>
when global variables get resolve ?<br>
need of volatile with compiler flag O0 ?<br>
	need to remove optimization for specific variable<br>
memory barrier in kernel<br>
net filters<br>
TCP handshake<br>
packet lifecycle<br>
how stp select root node ? based on mac addr<br>
diff snmp walk and bulk walk<br>
trap and alram<br>
need of makefile<br>


set 0 to diagnal elements in multi-dimension matrix
```
int nullit(int arr[][], size_t size)
{
	int i = 0;
	int j = 0;
	
	for(i = 0; i < size; i++) {
		for (j = 0; j < size; j++) {
			if ((i == j) || ((i == 0) && (j == size -1)) || ((i == size - 1) && (j = 0)) {
				arr[i][j] = 0;
			}
		}
	}
}

will work only for 3x3
```

remove node only with node pointer. (no reference to head pointer)
memory segment

List program
```
take ll reverse 

a b c d e f g h
a h c f e d g b

___ func()

int func (struct node *list)
{
    int i = 0, j = 0;
    struct node *current = NULL;
    strcu node *end = NULL;
    
    if (list == NULL) {
        return -1; //null head
    }

    current = list;
  
    while(current != NULL) {
        current = current->next;
    }
   
    end = current; //points end node
    
    current = list; //resetting first node
	
    while (current != NULL) {
        if (current->next != NULL) {
            new = end;
            end->prev->next = current->next;
			if (end->prev->prev != NULL) {
				end = end->prev->prev;
			}	
            new->next = current->next->next;
            new->prev = current;
            current->next = new;
            
            if (current->next->next != NULL) {
				current = current->next->next;
			}
        }
    }
	
	return 0;
}
```
What are all the restrictions for writing the kernel modules?<br>
	could not use printf, malloc will use kprintf and kmalloc<br>
How host know its IP?<br>
How router know its own packets becuase it does not have routing table for that.<br>
how vlagrind reports memory leak and how it know?<br>
how malloc works and its memory header?<br>
What symbol table consists?<br>
what is ELF and what it consists?<br>
What is best data-structure to maintain routing table?<br>
Type of IPC<br>
Diff of Socket and Shared Memory<br>
Ethernet field<br>
Swap bit from x to y<br>
```
num = 1011101110111011
ans   1011111111111011

mask = 111111111111111
a = 111111111111000
b = 111110000000000
mask = a^b = 0000001111111000
ans = num | mask
ans   1011111111111011
```
Remove duplicates in a list: 
- dont use loop
- can use merge sort to remove dups (not suitable for the list does not require sorting)
- can use hashing
```
1-->2-->2-->3
1-->2-->3

1-->1-->2-->3-->2
1-->2-->3

struct node {
    struct node *next;
    int data;
};

int remove_dups(struct node *list)
{
    int retavl = -1;
    struct node *curr = NULL;
    struct node *next = NULL;
    struct node *tmp = NULL;
    
    do {
        if (list == NULL) {
            fprintf(stderr, "list is null\n");
            retval = -1;
            break; 
        }

        while(curr != NULL) {
            curr = list;
            next = curr->next;

            while(next != NULL) {
                if (curr->data == next->data) {
                    //remove duplicate node
                    curr->next = next->next;
                    free(
                }
            }
        }

        if (curr->next == NULL) {
            /* list has only one element. and no duplicates. */
            fprintf(stderr, "only one element\n");
            retval = 0;
            break; 
        } else {
            next =

        }
    } while(0);

    return retval;
}
```
