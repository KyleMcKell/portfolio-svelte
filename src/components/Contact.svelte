<script lang="ts">
	import emailjs from '@emailjs/browser';
	import { toast } from '@zerodevx/svelte-toast';

	let disabled = false;

	function sendEmail(e: any) {
		e.preventDefault();

		if (disabled) {
			return toast.push('You already sent an email!', {
				theme: {
					'--toastBackground': 'var(--secondary-700)',
					'--toastBarBackground': 'var(--secondary-900)',
					'--toastTextColor': 'var(--text-primary)',
					'--toastFontWeight': '500'
				}
			});
		}

		disabled = true;

		emailjs.sendForm('gmail', 'contact-me', e.target, 'user_vManlYtWcUHq4SZAbx5T0').then(
			(result) => {
				toast.push('Email Sent!', {
					theme: {
						'--toastBackground': 'var(--primary-700)',
						'--toastBarBackground': 'var(--primary-900)',
						'--toastTextColor': 'var(--text-primary)'
					}
				});
				console.log(result);
			},
			(error) => {
				toast.push('Email not sent!', {
					theme: {
						'--toastBackground': 'var(--secondary-700)',
						'--toastBarBackground': 'var(--secondary-900)',
						'--toastTextColor': 'var(--text-primary)',
						'--toastFontWeight': '500'
					}
				});
				console.error(error);
			}
		);

		e.target.reset();
	}
</script>

<form action="submit" on:submit={sendEmail}>
	<h2>Contact Me!</h2>
	<section class="field name">
		<label for="name">Name</label>
		<input type="text" name="name" id="name" required />
	</section>

	<section class="field email">
		<label for="email">Email</label>
		<input type="email" name="email" id="email" required />
	</section>

	<section class="field subject">
		<label for="subject">Subject</label>
		<input name="subject" type="text" id="subject" required />
	</section>

	<section class="area message">
		<label for="message">Name</label>
		<textarea name="message" id="message" required />
	</section>

	<button type="submit" {disabled}>Send</button>
</form>

<style>
	form {
		max-width: 800px;
		flex: 1;
		display: grid;
		gap: 2rem;
		grid-template-columns: 1fr minmax(500px, 3fr) 1fr;
		grid-template-areas:
			'heading heading heading'
			'name message message'
			'email message message'
			'subject subject button';
	}

	h2 {
		color: var(--text-base);
		font-size: 2rem;
		grid-area: heading;
		text-align: center;
	}

	section.field {
		display: grid;
		max-height: 6rem;
	}

	.name {
		grid-area: name;
	}

	.email {
		grid-area: email;
	}

	.subject {
		grid-area: subject;
	}

	.message {
		grid-area: message;
	}

	input {
		padding: 0.5rem 1rem;
		font-size: 1rem;
		line-height: 1.5;
		border: none;
		border-radius: 5px;
		background-color: var(--gray-700);
		color: var(--text-base);
		margin-top: 0.3rem;
		font-family: inherit;
	}

	input:focus {
		outline: 3px solid var(--primary-600);
	}

	textarea {
		margin-top: 0.3rem;
		display: grid;
		padding: 0.5rem 1rem;
		font-size: 1rem;
		line-height: 1.5;
		width: 100%;
		min-height: calc(100% - 1.5rem);
		border: none;
		font-family: var(--font-base);
		border-radius: 5px;
		background-color: var(--gray-700);
		color: var(--text-base);
	}

	textarea:focus {
		outline: 3px solid var(--primary-600);
	}

	button {
		place-self: end;
		display: grid;
		place-content: center;
		max-height: 40px;
		border: none;
		padding: 1rem 3rem;
		border-radius: 4px;
		font-family: inherit;
		font-size: 1rem;
		font-weight: 500;
		color: var(--gray-800);
		background-color: var(--primary-800);
		transition: background-color 0.5s ease;
	}

	button:hover {
		cursor: pointer;
		box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
		background-color: var(--primary-600);
	}

	button:active {
		background-color: var(--primary-900);
	}

	button:focus {
		outline: 3px solid var(--primary-300);
	}

	button:disabled {
		background-color: var(--gray-500);
		opacity: 0.5;
		box-shadow: none;
	}

	@media (max-width: 1000px) {
		form {
			grid-template-columns: 1fr;
			grid-template-areas:
				'heading'
				'name'
				'email'
				'subject'
				'message'
				'button';
		}
	}

	@media (max-width: 466px) {
		h2 {
			text-align: revert;
		}
	}
</style>
