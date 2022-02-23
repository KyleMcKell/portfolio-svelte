<script lang="ts">
	import emailjs from '@emailjs/browser';
	import { toast } from '@zerodevx/svelte-toast';

	const errorToastTheme = {
		'--toastBackground': 'var(--secondary-700)',
		'--toastBarBackground': 'var(--secondary-900)',
		'--toastTextColor': 'var(--text-primary)',
		'--toastFontWeight': '500',
	};

	const successToastTheme = {
		'--toastBackground': 'var(--primary-700)',
		'--toastBarBackground': 'var(--primary-900)',
		'--toastTextColor': 'var(--text-primary)',
		'--toastFontWeight': '500',
	};

	let disabled = false;

	function sendEmail(e: SubmitEvent) {
		e.preventDefault();

		const typedTarget = e.target as HTMLFormElement;

		if (disabled) {
			return toast.push('You already sent an email!', {
				theme: errorToastTheme,
			});
		}

		const emailJSUser = import.meta.env.VITE_EMAILJS_USER_ID;

		if (typeof emailJSUser !== 'string') {
			return toast.push('Missing email credentials', {
				theme: errorToastTheme,
			});
		}

		emailjs.sendForm('gmail', 'contact-me', typedTarget, emailJSUser).then(
			(result) => {
				toast.push('Email Sent!', {
					theme: successToastTheme,
				});
				console.log(result);
			},
			(error) => {
				toast.push('Email not sent!', {
					theme: errorToastTheme,
				});
				console.error(error);
			}
		);

		typedTarget.reset();
		disabled = true;
	}
</script>

<form action="submit" on:submit={sendEmail}>
	<h2>Contact Me!</h2>
	<section class="field name">
		<label for="name">Name</label>
		<input type="text" name="name" id="name" required {disabled} />
	</section>

	<section class="field email">
		<label for="email">Email</label>
		<input type="email" name="email" id="email" required {disabled} />
	</section>

	<section class="field subject">
		<label for="subject">Subject</label>
		<input name="subject" type="text" id="subject" required {disabled} />
	</section>

	<section class="area message">
		<label for="message">Message</label>
		<textarea name="message" id="message" required {disabled} />
	</section>

	<button type="submit" {disabled}>Send</button>
</form>

<style>
	form {
		max-width: 600px;
		flex: 1;
		display: grid;
		gap: 2rem;
		grid-template-columns: 1fr minmax(250px, auto) 1fr;
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
		min-height: calc(100% - 1.8rem);
		border: none;
		font-family: var(--font-base);
		border-radius: 5px;
		background-color: var(--gray-700);
		color: var(--text-base);
	}

	textarea:focus {
		outline: 3px solid var(--primary-600);
	}

	textarea:disabled,
	input:disabled {
		background-color: var(--gray-600);
		opacity: 0.4;
		box-shadow: none;
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
