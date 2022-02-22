<script>
	const linkA = [
		{ href: '/about', text: 'About us' },
		{ href: '/contacts', text: 'Contacts' },
		{ href: '/projects', text: 'Projects' },
		{ href: '/jason-scott-lee', text: 'Jason Scott Lee' }
	];

	const linkB = [
		{ href: 'https://www.xarbinindustries.com', text: 'Xarbin Industries Homepage' },
		{ href: 'https://www.issfworld.org', text: 'ISSF Homepage' },
		{
			href: 'mailto:stacyakana@teamxhawaii.org',
			text: 'stacyakana@teamxhawaii.org'
		}
	];

	const linkLists = [
		{ list: linkA, head: 'Main Links' },
		{ list: linkB, head: 'Other Links' }
	];
</script>

<footer class="none">
	<div class="container-fluid pt-5">
		<div class="row">
			<div class="col-md-6 pt-5">
				<h2 class="footer-heading display-1">Team X Hawaii</h2>
				<h3 class="footer-heading display-3">Contact us!</h3>
			</div>
			<div class="col-md-6">
				{#each linkLists as list}
					<div class="p-2 container-fluid">
						<ul class="bg-primary footer-list">
							<li class="text-center">
								<h3>{list.head}</h3>
							</li>
							{#each list.list as link}
								<li class="text-center">
									<a href={link.href} class="footer-link">{link.text}</a>
								</li>
							{/each}
						</ul>
					</div>
				{/each}
			</div>
		</div>
	</div>
</footer>
