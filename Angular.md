

# template refs and context binding

you can use the 


# using templates WITHIN a parent and

```.html
<shared>
	[inputTemplate]=customBananaPanel
</shared>

<ng-template #customBananaPanel>
	<myPanel [namesBanana]=input>
	</myPanel>
</ng-template>

```

The RELATTIONship between the parent using the myPanel is PRESERVERVED even if we are passing WHERE that code is rendered inside of the 'shared' component!

