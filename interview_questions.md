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

what if dest mac is not match in switch and router ?
fragmentation in ip stack ?
what if frame exceeds the mtu size ?
	if fragmentation enable, the frame get fragment
max port no ?
can we set own client port no ?
what listen will do ?
	monitor incomming req and create passive sockets
How global values are acceseddd in parent and child ?
how mutex values in acccess by two process (bcz two procs are not communicate) ?
is static varible with same name is cause compilation error ?
when global variables get resolve ?
need of volatile with compiler flag O0 ?
	need to remove optimization for specific variable
memory barrier in kernel
net filters
TCP handshake 
packet lifecycle
how stp select root node ? based on mac addr
diff snmp walk and bulk walk
trap and alram
need of makefile
