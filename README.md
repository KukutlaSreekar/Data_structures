#binary_search_tree

#include<stdio.h>

#include<stdlib.h>

struct node{

int dt;

struct node*l;

struct node*r;

}*root=NULL,*tp=NULL,*nn=NULL;

void insert() {

 int val, ch;

 do {

 nn = (struct node*)malloc(sizeof(struct node));

 printf("Enter value: ");

 scanf("%d", &nn->dt);

 nn->l = NULL;

 nn->r = NULL;

 if (root == NULL) {

 root = nn; 

 } else {

 tp = root;

 while (1) {

 if (nn->dt < tp->dt) {

 if (tp->l != NULL) {

 tp = tp->l; 

 } else {

 tp->l = nn; 

 break;

 }

 } else {

 if (tp->r != NULL) {

 tp = tp->r; 

 } else {

 tp->r = nn; 

 break;

 }}}}

 printf("Enter 0 to exit, other to continue: ");

 scanf("%d", &ch);

 } while (ch != 0);}

void search() {

 int s;

 printf("\nEnter value to search: ");

 scanf("%d", &s);

 tp = root;

 while (tp != NULL) {

 if (tp->dt == s) {

 printf("Element is Found.....");

 return;

 } else if (s < tp->dt) {

 tp = tp->l; 

 } else {

 tp = tp->r; }}

 printf("Element is Not found...");}

void display(struct node* tp){

if(tp!=NULL){

display(tp->l);

printf("%d\t",tp->dt);

display(tp->r);

}}

int main(){

insert();

display(root);

search();

display(root);

return 0;}
